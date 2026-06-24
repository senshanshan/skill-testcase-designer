# Test Dimensions

Use these nine domains as the top-level classification. The eleven detailed review areas map into them as follows.

## Domain Mapping

| Detailed area | Primary domain | Secondary domain |
|---|---|---|
| Basic structure and parsing | Functional | Compatibility |
| Trigger accuracy | Trigger | User Experience |
| Workflow execution | Workflow | Functional |
| Scripts, resources, and tools | Functional | Exception |
| Professional capability and result quality | Functional | User Experience |
| Input boundaries and abnormal cases | Exception | Security |
| Compatibility | Compatibility | Regression |
| Security and compliance | Security | Exception |
| Performance and stability | Performance | Regression |
| User experience | User Experience | Trigger |
| Regression and release testing | Regression | Functional |

## Domain Definitions

### Functional

Verify that the Skill can be loaded, understood, and used to complete its intended core tasks.

Typical checks:
- `SKILL.md` metadata and body can be parsed.
- Directory structure and referenced files exist.
- Scripts, references, assets, and tools work as expected.
- Output format and professional result quality match requirements.

### Trigger

Verify whether the Skill is invoked in the right situations.

Typical checks:
- Explicit invocation by name.
- Implicit invocation from user intent.
- Similar-but-unrelated requests that must not trigger.
- Ambiguous inputs that should lead to clarification.
- Multi-Skill conflicts, false positives, and false negatives.

### Workflow

Verify that the Skill follows the required process after it is triggered.

Typical checks:
- Required files are read before action.
- Steps run in the intended order.
- Conditional branches are selected correctly.
- Multi-turn state is preserved while the task is active.
- Skill-specific context does not leak into later unrelated tasks.

### Compatibility

Verify that the Skill behaves consistently across supported environments.

Typical checks:
- Different model families interpret the Skill consistently.
- Long Skill content does not drop critical instructions.
- Windows, Linux, and macOS path conventions work.
- Chinese, English, mixed-language, and encoding cases work.
- Framework or runtime version differences are handled.

### Exception

Verify graceful behavior when inputs or dependencies are abnormal.

Typical checks:
- Empty, malformed, conflicting, or oversized input.
- Missing references, unsupported file formats, broken paths.
- Permission failures, tool failures, network timeouts, and API rate limits.
- Clear fallback behavior and useful error messages.

### Security

Verify that the Skill resists malicious or unsafe behavior.

Typical checks:
- Prompt injection in user text or uploaded files.
- Requests to reveal system prompts, internal Skill text, secrets, or hidden paths.
- Attempts to access or modify files outside the allowed scope.
- Dangerous commands, destructive script behavior, or untrusted code execution.
- Professional compliance boundaries for high-risk domains.

### Performance

Verify that the Skill is efficient enough for real use.

Typical checks:
- End-to-end execution time.
- Token consumption from Skill and reference loading.
- Tool call count and repeated reads.
- Script memory usage and long-running behavior.
- Concurrent execution or repeated trigger stability.

### User Experience

Verify that the Skill is understandable and usable from the user's perspective.

Typical checks:
- Name and description make the capability clear.
- Clarifying questions are specific and useful.
- Final output is readable, actionable, and appropriately structured.
- Failure messages explain cause, impact, and next step.
- Generated files or deliverables are easy to open and use.

### Regression

Verify that updates do not break previously working behavior.

Typical checks:
- Historical test cases still pass.
- Metadata migration works.
- Trigger rules remain stable.
- Output format does not drift unexpectedly.
- Dependencies and templates remain compatible.

## Classification Rule

Classify each test case by the primary failure it is meant to expose. Add a secondary domain only when it materially helps triage.
