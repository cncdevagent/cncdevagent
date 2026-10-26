# Verification note

Use only sanitized technical details. Omit personal names, phone numbers, email addresses, account connections, customer records, credentials, and local user paths. Do not attach raw logs or screenshots without reviewing them for identifying information.

**Job:** <non-identifying reference>
**Date:** <YYYY-MM-DD>
**Status:** <Draft / Checks passed / Verified with limitations / Blocked>

## Summary and agreed result

<Observed problem, expected behavior, and agreed acceptance checks.>

## Reproduction and environment

<Steps, observed result before the change, runtime versions, and relevant configuration. Use synthetic data.>

## Root cause and change

<Cause supported by evidence, files changed, and why the change addresses it. Link a diff only after checking its privacy.>

## Verification

| Check | Command or method | Observed result | Evidence and limitations |
| --- | --- | --- | --- |
| Original reproduction | <method> | <not run / pass / fail> | <sanitized evidence> |
| Relevant regression checks | <command> | <not run / actual count> | <what was covered> |
| Agreed acceptance checks | <method> | <not run / pass / fail> | <remaining gaps> |

Do not infer that an unrelated flow works because its files were unchanged. Distinguish local results, CI results, and production verification.

## Impact, limitations, and rollback

<Affected behavior, untested cases, remaining risks, and exact rollback steps. State when deployment or rollback was not tested.>

## Review record

- Automated checks: <actual checks and date, or not performed>
- Independent human review: <not performed / pending / completed, with actual scope and date>
- Working method: <accurate description of assistance used when relevant to the agreement>

Use the CNC Dev brand in public records. Do not invent an engineer, reviewer, client, or approval.
