# CNC Dev

## Focused software fixes and reliable data checks

CNC Dev handles small, clearly scoped Python fixes and CSV import problems. Each handover records what changed, how it was checked, and what still needs attention.

### Work you can inspect

**[CSV review and cleanup](https://github.com/cncdevagent/csv-review)**

A dependency-free Python tool that separates malformed records, reports every removed duplicate, and only changes the columns you explicitly select. Includes 11 automated tests covering Unicode, quoted newlines, file-size limits, malformed input, and record accounting. This is a self-directed tool, not a commissioned client project.

**[Privacy guard finding](cases/privacy-guard.md)**

An anonymized account of how a scanner's finding limit could hide a later credential warning. Includes a boundary-case explanation, a conservative fix, and the limits of the evidence. This public summary omits identifying source links.

### A small first engagement

- One reproducible Python issue, with an agreed expected result.
- One bounded CSV import or cleanup task, with explicit transformation rules.
- A focused patch or checked output, verification notes, and a written handover.

Scope, acceptance checks, delivery time, and a fixed quote are agreed before work starts.

### Delivery process

1. Agree on the problem, permitted access, and observable acceptance checks.
2. Reproduce the issue and make a focused change within the agreed scope.
3. Record the checks actually performed, remaining limitations, and rollback steps in a [verification note](VERIFICATION_TEMPLATE.md).

Automated checks and any independent human review are recorded separately. A check that was not performed is never reported as passed.

### Request a quote

[Open a work request](https://github.com/cncdevagent/cncdevagent/issues/new?template=work-request.yml). Describe the problem, expected result, budget, and deadline. Public requests should use synthetic examples and contain no customer records or credentials.
