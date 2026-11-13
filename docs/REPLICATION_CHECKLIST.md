# Reproducing the lead intake workflow

1. Import `workflows/01-w1-reliable-lead-intake-deduplication.json`.
2. Create the n8n Data Tables referenced by the workflow and update node-specific table identifiers.
3. Replace the outbound HTTP endpoint with your own authorized test receiver or mock CRM.
4. Submit a synthetic lead with valid name, email and contact details.
5. Resubmit the exact lead and inspect whether the saved records, CRM calls and response remain idempotent.
6. Submit a lead with missing fields, inspect the exception table and verify the caller receives the expected response.
7. Simulate a downstream API error and confirm that the failure path records sufficient information for recovery.

**Evidence warning:** This exported flow demonstrates the orchestration structure. Strong idempotency, recovery guarantees and success metrics must be established with live tests.
