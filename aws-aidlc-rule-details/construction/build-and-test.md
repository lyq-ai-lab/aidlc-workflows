# Build and Test

**Purpose**: Build applicable units and artifacts, verify implemented behavior against approved requirements, and run the existing checks selected for this task

## Prerequisites
- Code Generation must be complete for all units
- All code artifacts must be generated
- Project is ready for build and verification

---

## Step 1: Determine Build and Verification Scope

Use the approved requirements, unit designs, and existing project commands to identify:
- Units and artifacts to build
- Implemented behaviors and their expected results
- Existing checks applicable to the change
- Runtime, inputs, and dependencies needed for execution
- Evidence needed to assess the agreed completion criteria

---

## Step 2: Generate Build Instructions

Create `aidlc-docs/construction/build-and-test/build-instructions.md`:

```markdown
# Build Instructions

## Prerequisites
- **Build Tool**: [Tool name and version]
- **Dependencies**: [List all required dependencies]
- **Environment Variables**: [List required env vars]
- **System Requirements**: [OS, memory, disk space]

## Build Steps

### 1. Install Dependencies
\`\`\`bash
[Command to install dependencies]
# Example: npm install, mvn dependency:resolve, pip install -r requirements.txt
\`\`\`

### 2. Configure Environment
\`\`\`bash
[Commands to set up environment]
# Example: export variables, configure credentials
\`\`\`

### 3. Build All Units
\`\`\`bash
[Command to build all units]
# Example: mvn clean install, npm run build, brazil-build
\`\`\`

### 4. Verify Build Success
- **Expected Output**: [Describe successful build output]
- **Build Artifacts**: [List generated artifacts and locations]
- **Common Warnings**: [Note any acceptable warnings]

## Troubleshooting

### Build Fails with Dependency Errors
- **Cause**: [Common causes]
- **Solution**: [Step-by-step fix]

### Build Fails with Compilation Errors
- **Cause**: [Common causes]
- **Solution**: [Step-by-step fix]
```

---

## Step 3: Execute Build and Runtime Verification

- Follow `build-instructions.md` for the applicable units and artifacts
- Start the application or exercise the unit through its existing public entry points
- Compare observed behavior with the approved requirements identified in Step 1
- Collect actual build output, runtime results, and failures for the summary

---

## Step 4: Run Applicable Existing Checks

- Select existing project check commands relevant to the scope identified in Step 1
- Run those commands using the documented project setup
- Where execution needs explanation, create the corresponding instruction file under `aidlc-docs/construction/build-and-test/` with the existing command, setup, expected result, and cleanup
- Review failures against approved requirements and actual runtime conditions
- Address implementation issues within the approved scope and rerun the affected checks

---

## Step 5: Verify Performance Requirements (If Applicable)

- Use existing measurement tools and runtime capabilities to assess confirmed performance requirements
- Record observed measurements alongside the requirement targets in the summary

---

## Step 6: Verify Additional Requirements (As Needed)

- Use existing commands and actual operation to assess applicable integration, contract, security, and user-workflow requirements
- Document selected procedures where execution needs explanation
- Record the observed results and remaining verification scope in the summary

---

## Step 7: Generate Build and Verification Summary

Create `aidlc-docs/construction/build-and-test/build-and-test-summary.md`:

```markdown
# Build and Test Summary

## Build Status
- **Build Tool**: [Tool name]
- **Build Status**: [Success/Failed/Pending]
- **Build Artifacts**: [List artifacts]
- **Build Time**: [Duration]

## Verification Results

### [Approved requirement or scenario]
- **Requirement**: [Reference to the approved requirement]
- **Expected Result**: [Behavior specified by the requirement]
- **Observed Result**: [Actual runtime behavior]
- **Evidence**: [Output, artifact, or observation supporting the result]
- **Status**: [Verified/Failed/Pending]

## Existing Checks
- **Command**: [Existing command executed]
- **Observed Result**: [Actual output and outcome]
- **Status**: [Passed/Failed/Pending]

## Performance and Additional Requirements (If Applicable)
- **Requirement**: [Confirmed target or constraint]
- **Observed Result**: [Actual measurement or observation]
- **Status**: [Verified/Failed/Pending]

## Remaining Verification
- **Scope**: [Behavior or requirement awaiting verification]
- **Reason**: [Runtime, dependency, or other execution condition]
- **Impact on Completion**: [Effect on the agreed completion criteria]

## Overall Status
- **Build**: [Success/Failed/Pending]
- **Verified Scope**: [Requirements supported by actual results]
- **Completion Status**: [Assessment against the agreed completion criteria]
- **Ready for Operations**: [Yes/No]

## Next Steps
[Address confirmed implementation issues or proceed according to the recorded results]
```

---

## Step 8: Update State Tracking

Update `aidlc-docs/aidlc-state.md`:
- Record actual build and verification results
- Mark Build and Test stage complete when the agreed completion criteria are satisfied
- Update current status with remaining issues and the next action

---

## Step 9: Present Results to User

Present completion message in this structure:
     1. **Completion Announcement** (mandatory): Always start with this:

```markdown
# 🔨 Build and Test Complete
```

     2. **AI Summary** (optional): Provide structured bullet-point summary of build and verification results
        - Format: "Build and verification produced the following results:"
        - List build status and artifacts
        - List verified behaviors, existing checks executed, and remaining verification
        - List generated instruction files
        - DO NOT include workflow instructions ("please review", "let me know", "proceed to next phase", "before we proceed")
        - Keep factual and content-focused
     3. **Formatted Workflow Message** (mandatory): Always end with this exact format:

```markdown
> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the build and test summary at: `aidlc-docs/construction/build-and-test/build-and-test-summary.md`



> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for corrections to the build or verification results based on your review
> ✅ **Approve & Continue** - Approve the recorded results and proceed to **Operations**

---
```

---

## Step 10: Log Interaction

**MANDATORY**: Log the stage completion in `aidlc-docs/audit.md`:

```markdown
## Build and Test Stage
**Timestamp**: [ISO timestamp]
**Build Status**: [Success/Failed/Pending]
**Verification Status**: [Assessment against the agreed completion criteria]
**Remaining Verification**: [Scope and execution conditions]
**Files Generated**:
- build-instructions.md
- build-and-test-summary.md
- [Execution instructions for selected existing checks, as applicable]

---
```
