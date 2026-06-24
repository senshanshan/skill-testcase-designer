---
name: skill-testcase-designer
description: Generate structured QA test cases for Codex Skills, agent capabilities, and professional agent releases. Use when the user wants to design, review, classify, or export test cases for a Skill/agent based on SKILL.md, capability descriptions, workflows, scripts, references, assets, trigger rules, safety requirements, or release-readiness criteria.
---

# Skill Testcase Designer

Use this skill to turn a Skill or professional agent capability into a practical test suite.

## Workflow

1. Collect available inputs:
   - Target Skill name and `SKILL.md`, if available.
   - Capability description, intended users, trigger examples, and non-trigger examples.
   - Directory structure, scripts, references, assets, external APIs, and file outputs.
   - Release target, supported platforms, model/runtime assumptions, and risk level.

2. If key information is missing, make conservative assumptions and list them. Ask only when missing information would materially change the test design.

3. Read `references/test-dimensions.md` when classifying coverage, mapping detailed checks into the main test domains, or explaining the coverage strategy.

4. Read `references/testcase-template.md` when generating test cases or a reusable test case table.

5. Generate test cases using these default domains:
   - Functional
   - Trigger
   - Workflow
   - Compatibility
   - Exception
   - Security
   - Performance
   - User Experience
   - Regression

6. Prioritize cases:
   - P0: Core path, release blocker, security red line, or professional accuracy risk.
   - P1: Common real-world complex path.
   - P2: Edge case, degradation path, compatibility issue, or lower-frequency risk.
   - P3: Stress, polish, rare case, or long-tail regression.

7. For professional agents, always include coverage for:
   - Trigger accuracy, including explicit trigger, implicit trigger, false positive, and false negative.
   - Professional correctness, including terminology, calculations, standards, assumptions, and limitations.
   - Prompt injection and malicious content inside user input or files.
   - Context persistence during the task and context release after the task.
   - Resource and file access boundaries.
   - Regression against historical examples.

## Output Rules

- Prefer a concise coverage summary followed by a structured test case table.
- Use the user's requested format if specified.
- If no format is specified, use the fields from `references/testcase-template.md`.
- Include assumptions, out-of-scope items, and unresolved questions when relevant.
- Keep each test case executable: include input, preconditions, expected behavior, and pass criteria.
- Separate "should trigger" and "should not trigger" cases.
- Do not over-generate low-value cases; prioritize risks that can break real user workflows.
