# Patch Manifest Template

## Use

Use one manifest with each temporary patch at `projects/<project-id>/active/<task-id>/patches/manifest.md` in a private development-state repository. A manifest makes a patch auditable and safe to apply; it does not make the patch a substitute for a product-repository commit.

Record only observed details. Do not include secrets or use a manifest to conceal excluded changes.

---

# Patch Manifest: <Task Title>

## Identity

- Project ID: `<project-id>`
- Task ID: `<task-id>`
- Created: `<UTC timestamp>`
- Source device or environment: `<device-id or environment>`

## Product-Repository Base

- Remote: `<remote URL or configured remote name>`
- Branch at capture: `<branch>`
- Base commit: `<full commit SHA>`
- Expected destination state before application: <Required branch, commit, and working-tree condition>

## Patch Files and Order

1. `<001-base-short-sha.patch>` — SHA-256: `<hash>`

## Coverage

- Included changes: <Paths and change categories>
- Explicitly excluded changes: <Untracked, ignored, generated, binary, local-configuration, or other excluded items>
- Coverage verification: <How inclusion and exclusion were checked>

## Application and Validation

- Compatibility check: <Dry-run or equivalent check before applying>
- Apply order and command: <Exact authorized method>
- Expected diff after application: <Summary or comparison command>
- Required validation: <Commands and focused manual checks>

## Outcome and Retention

- Status: `<pending | applied | failed | retired>`
- Application result: <Observed result, or pending>
- Retire or archive when: <Condition and retention decision>
