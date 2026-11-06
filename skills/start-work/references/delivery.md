# Delivery

Use this module when the requested endpoint includes a Git, PR, release, or
external action. Apply [Contract and permissions](contract.md#permissions).

1. Perform authorized delivery actions and verify the resulting state. For PR
   delivery, use the actual PR or stack base and inspect the complete final diff
   before describing it. Verify the remote head, required checks for that head,
   unresolved review threads, and merge state after the last push. Report pending
   or unavailable evidence explicitly. Stop at the requested endpoint.
   Any additional workflow must fit the task and preserve these permissions.

## Report the observed state

For code work, lead with the [council report](council.md#report), then the actual
delivery state and evidence for that action. For other work, report the requested
outcome, verification, remaining risks, and relevant branch or PR state. Follow
the project's local handoff convention.
