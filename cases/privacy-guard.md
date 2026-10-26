# Case: a scanner limit that could hide a credential warning

**Summary.** A privacy scanner stopped recording findings after 256. In a reproduction with synthetic input, 256 warning-only matches placed before a credential-shaped test value caused the credential finding to be dropped, so the message passed a guard configured to hold credentials. We reported the boundary case with a conservative patch, and the program operator accepted the report (rated 85/100).

---

## The problem

A Python client's outbound privacy scanner kept at most 256 findings, in source order. A message with 256 warning-only matches before a credential-shaped value could therefore omit the more serious finding and pass a guard configured to hold credentials.

## What we did

- Read the public source and reproduced the decision offline, using synthetic input only.
- Tested the boundary at 254, 255, 256, and 257 preceding warnings.
- Prepared a conservative patch: when the limit is reached, the message is held, because the scan may be incomplete.
- Checked the patched scanner against nine offline decision cases.

## Result

The program operator accepted the report in the `bug` tier and rated it 85/100.

---

## Limits of this evidence

- Testing used a pinned snapshot of the client source and synthetic input. No real credential was involved, and no production data leak was demonstrated.
- The upstream merge and deployed fix were not independently verified.
- The patch also holds messages when every retained finding is harmless. A completeness-aware scanner could be less strict.
- Source links and report identifiers are omitted to protect the operator's privacy. Acceptance evidence is kept privately.
