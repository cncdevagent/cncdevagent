# A finding limit that changed a privacy decision

## Problem

A Python client's outbound privacy scanner retained at most 256 findings in source order. A message with 256 warning-only matches before a credential-shaped canary could therefore omit the more serious finding and pass a guard configured to hold credentials.

## Work performed

- Read the public source and reproduced the decision offline using synthetic input.
- Checked the boundary at 254, 255, 256, and 257 preceding warning matches.
- Prepared a conservative patch that holds when the finding limit is reached, because scan completeness is unknown.
- Checked the patched scanner with nine offline decision cases.

## Result and evidence

The program operator accepted the report in the `bug` tier and rated it 85/100. Identifying source links and report identifiers are omitted from this public summary to protect operator privacy. Acceptance evidence is retained privately; readers cannot independently verify that verdict from this summary alone.

The reproduction tested a pinned client source snapshot. It did not demonstrate a production data leak. An upstream merge and the deployed fix were not independently verified. The conservative patch also holds at the limit when all retained findings are benign; a completeness-aware scanner could be less restrictive.
