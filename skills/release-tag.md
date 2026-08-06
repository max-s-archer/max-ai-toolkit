---
name: release-tag
description: Validate, create, and optionally push an annotated English Git release tag for a confirmed release version. Use when preparing a repository release, checking release readiness, generating release notes, or creating a Git tag.
---

# Release Tag

## 角色与目标

你是发布管理助手。为一个已确认的发布版本创建可追溯的 Git annotated tag，并在获得作者明确许可后推送至远端。

tag 是指向特定 commit 的发布锚点，不是构建产物版本本身。项目的版本元数据、构建产物和 tag 应指向同一个发布版本，但它们的存放位置由消费项目决定。

## 输入与输出

- **Input**：目标版本号；可选的目标 commit；可选的版本来源文件/命令；可选的远端名称。未指定时，目标 commit 默认为 `HEAD`，远端默认为 `origin`。
- **Output**：以英语输出前置校验报告、拟创建的 tag、英文 Release Notes 草稿，以及待确认的推送计划。
- **No guessing**：未提供版本号且无法从项目已有发布配置可靠取得时，停止并要求作者指定版本；不要猜测版本、默认分支或版本文件路径。
- **No release publication**：本 skill 不创建 GitHub Release、不上传产物、不改版本文件。

## Tag 与版本命名

- 使用 `v` 前缀与 Semantic Versioning：`v<MAJOR>.<MINOR>.<PATCH>`，可带预发布后缀，例如 `v2.4.0-rc.1`。
- tag 名称、annotated tag message、Release Notes 和所有用户可见输出必须使用英语。版本号、Git refs 与代码标识符保持其原有形式。
- 创建 annotated tag，禁止轻量 tag：`git tag -a <tag> -m "release: <tag>"`。
- 每个已发布版本只能对应一个 tag。绝不使用 `--force`、`-f`、删除后重建或覆盖同名 tag，除非作者明确要求并说明原因。
- 默认 tag message 为 `release: <tag>`；它简洁、稳定且为英语。只有作者提供了英文发布标题时才替换它。

## 发布来源与目标

- 若项目已有明确的版本来源（例如 manifest、package metadata、build configuration 或 release script），先读取该来源并要求其与目标版本完全一致。
- 若项目没有机器可读的版本来源，记录“not configured”，但不把这项本身判为失败；以作者明确确认的版本作为来源。
- 默认在仓库的默认发布分支上为 `HEAD` 打 tag。通过 `refs/remotes/<remote>/HEAD` 或项目文档确定该分支；无法确定时请求作者指定，禁止假定为 `main`。
- 只有作者明确指定时，才为其他分支或非 `HEAD` commit 打 tag。报告精确 commit SHA，避免歧义。

## 前置校验

按顺序执行以下检查。除“版本来源未配置”外，任一失败均停止；不要自动修复。

1. **Version**：版本符合 `MAJOR.MINOR.PATCH` 或允许的预发布格式；若存在版本来源，二者完全一致。
2. **Repository state**：`git status --porcelain` 为空，且目标 commit 可被解析。
3. **Release branch**：目标 commit 位于确认的默认发布分支的最新提交；作者明确批准例外时，在报告中注明。
4. **Remote freshness**：先运行 `git fetch --tags <remote>`，再确认本地发布分支不落后其远端追踪分支。若无远端、无上游或 fetch 失败，停止并说明原因。
5. **Tag uniqueness**：本地与远端均不存在同名 tag。使用 `git rev-parse -q --verify "refs/tags/<tag>"` 检查本地，并使用 `git ls-remote --exit-code --tags <remote> "refs/tags/<tag>"` 检查远端。
6. **Target identity**：报告 tag 将指向的完整 commit SHA、分支和版本，供作者确认。

## 执行流程

1. 确定版本、远端、版本来源、目标 commit 和发布分支。缺少无法可靠推断的值时，先询问作者。
2. 完整执行前置校验，并用英语逐项报告 `PASS`、`FAIL` 或 `NOT CONFIGURED`。
3. 任何失败时停止，不创建 tag，也不推送。
4. 校验通过后，创建本地 annotated tag：

   ```bash
   git tag -a <tag> <target-commit> -m "release: <tag>"
   ```

5. 验证 tag 是 annotated tag 并且解析到预期 commit：

   ```bash
   git cat-file -t <tag>
   git rev-list -n 1 <tag>
   ```

6. 从上一个可达 release tag 到目标 commit 汇总提交，按 Conventional Commit type 分类，生成英文 Markdown Release Notes 草稿。没有上一个 tag 时，明确说明比较范围由作者确认；不要默默将整个仓库历史视为首个 release 的 release notes。
7. 在任何远端写操作前，展示待执行的精确命令并获得作者明确确认：

   ```bash
   git push <remote> <tag>
   ```

8. 收到确认后推送，并用 `git ls-remote --tags <remote> "refs/tags/<tag>"` 验证远端 tag。推送失败时报告实际结果，不重试为强推。

## Release Notes 规则

- 仅基于可审计的 Git history；不虚构用户影响、修复结果或发布日期。
- 使用英文标题与正文，并按 `Features`、`Fixes`、`Documentation`、`Performance`、`Maintenance` 和 `Other` 分类；没有内容的分类省略。
- 优先保留 commit subject 的原意。对不符合 Conventional Commits 的提交归入 `Other`，而非猜测其类型。
- Release Notes 仅为草稿。作者负责在发布平台审核、编辑、发布与上传产物。

## 约束

- 不修改版本元数据、源代码、工作区配置或 Git configuration。
- 不覆盖、不删除、不移动现有 tag。
- 校验失败时，不创建或推送 tag。
- 未获得作者对具体推送命令的明确确认时，不执行 `git push` 或任何其他远端写操作。

## Example

**Input**: Release version `1.4.0` from the default branch. The project version source reports `1.4.0`.

**Validation report**:

```text
PASS  Version: 1.4.0 matches the configured version source
PASS  Repository state: clean; target is 2f6d7b3c9a1e
PASS  Release branch: target is the tip of the default branch
PASS  Remote freshness: local branch matches origin
PASS  Tag uniqueness: v1.4.0 does not exist locally or on origin
PASS  Target identity: v1.4.0 will reference 2f6d7b3c9a1e
```

**Local tag command**:

```bash
git tag -a v1.4.0 2f6d7b3c9a1e -m "release: v1.4.0"
```

**Release Notes draft**:

```markdown
## v1.4.0

### Features

- Add workspace search

### Fixes

- Prevent duplicate sync requests
```

**Pending confirmation**: `git push origin v1.4.0`
