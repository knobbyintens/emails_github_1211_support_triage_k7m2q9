# Support Escalation Triage Policy

This repository tracks engineering work produced by customer escalations from the
support mailbox folder `emails_github_1211_support_escalations_k7m2q9`.

## Priority

Determine the priority from `Affected users` and the escalation description:

| Priority | Rule |
| --- | --- |
| **P1** | `Affected users` >= 500 **or** the description mentions an outage, data loss, data corruption, or a security breach |
| **P2** | `Affected users` >= 50 and not P1 |
| **P3** | everything else |

## Duplicate handling

* An escalation is a duplicate **only** when an **open** issue in this repository
  contains the same `Error signature` in its body.
* Closed or resolved issues never count as duplicates.
* Duplicate handling takes precedence over the priority rules: for a duplicate,
  add a comment to the existing issue with the escalation ID and the customer
  name, regardless of its priority. Do not open a new issue.

## New issues

* For a non-duplicate P1 or P2 escalation, open an issue titled
  `[<PRIORITY>] <component>: <short summary>`.
* The body must record the escalation ID, customer, component, error signature,
  affected users and first-observed time.
* P1 issues must be assigned to the on-call engineer `knobbyintens`.
* P2 issues must not be assigned to anybody.

## Monitor only

Non-duplicate P3 escalations are reported in the triage report only. No issue
and no comment is created for them.

## Digest and report

* Send one digest email per batch to the support mailbox (`moorea@mcp.com`)
  with a subject containing `Triage Digest`. The body lists every P1 escalation
  ID from the batch.
* Produce `escalation_triage_report.csv` with one row per escalation.
