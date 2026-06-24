# Test Case Template

Use this table unless the user requests another format.

| Field | Meaning |
|---|---|
| Case ID | Stable identifier, such as `TC-FUNC-001` |
| Domain | Functional, Trigger, Workflow, Compatibility, Exception, Security, Performance, User Experience, or Regression |
| Priority | P0, P1, P2, or P3 |
| Test item | The specific capability or risk being tested |
| Preconditions | Required setup, files, tools, credentials, or context |
| User input | The exact user message or file/input description |
| Expected trigger | Should trigger, should not trigger, or conditional |
| Expected process | Key steps, file reads, tool calls, or workflow behavior |
| Expected result | Required output, file, answer, refusal, or error behavior |
| Pass criteria | Observable standard for pass/fail |
| Risk note | Why this case matters or what failure would affect |

## Case ID Prefixes

- Functional: `TC-FUNC`
- Trigger: `TC-TRIG`
- Workflow: `TC-WORK`
- Compatibility: `TC-COMP`
- Exception: `TC-EXC`
- Security: `TC-SEC`
- Performance: `TC-PERF`
- User Experience: `TC-UX`
- Regression: `TC-REG`

## Minimum Recommended Coverage

For a lightweight release, generate at least:
- 3 Functional cases
- 4 Trigger cases: explicit trigger, implicit trigger, false positive, false negative
- 2 Workflow cases
- 2 Exception cases
- 3 Security cases: prompt injection, sensitive leakage, file boundary
- 1 Performance case
- 1 User Experience case
- 2 Regression cases

For a professional or high-risk agent, expand Functional, Security, and Regression coverage first.
