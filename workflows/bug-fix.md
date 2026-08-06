# Bug-Fix Workflow

## Purpose

Correct observed behavior by establishing evidence, identifying the relevant cause, applying the smallest reliable fix, and preventing regression where practical.

## Inputs

- Observed behavior, expected behavior, and available reproduction evidence
- Affected project context, environment, version, and logs or diagnostics when available
- Known impact, urgency, and constraints

## Workflow

### 1. Establish the symptom

Describe the observed and expected behavior precisely. Reproduce the issue when possible and record the environment, inputs, and conditions that distinguish the failure from normal behavior. Do not treat an unverified report as a confirmed root cause.

### 2. Assess impact and scope

Identify affected users, components, data, compatibility boundaries, and release risk. Determine whether containment or rollback is needed before a permanent fix. Keep the investigation focused on evidence relevant to the symptom.

### 3. Identify the cause

Inspect the relevant implementation, configuration, history, and diagnostics. Form and test hypotheses until the cause is supported by evidence, or report the remaining uncertainty explicitly.

### 4. Implement the smallest reliable fix

Change the responsible behavior or boundary rather than masking the symptom. Avoid unrelated refactors. Re-check current files and working-tree state before editing, especially when more than one environment or contributor may be active.

### 5. Validate regression protection

Confirm that the reproduction no longer fails and that relevant expected behavior still works. Add or update automated coverage when it is practical and valuable; otherwise document the focused manual validation performed.

### 6. Capture reusable learning

Update product documentation or decisions when the fix changes a documented behavior or reveals a durable constraint. Extract a generalized lesson to the Toolkit only when it is proven useful beyond the current product.

## Completion criteria

- The symptom, expected behavior, and evidence are recorded accurately.
- The fix addresses an evidenced cause or clearly states residual uncertainty.
- Regression validation matches the risk and affected boundary.
- Any needed product documentation or reusable learning is handled deliberately.
