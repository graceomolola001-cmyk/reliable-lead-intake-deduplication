# Node-by-node lead-intake map

The 11-node `W1 - Reliable Lead Intake & Deduplication` workflow includes:

| Node | Role |
| --- | --- |
| Webhook | Receives prospect data |
| Normalize & Validate Leads | Checks and structures incoming fields |
| If | Routes according to validation |
| HTTP Request | Calls an external test CRM or API |
| Edit Fields | Standardizes response fields |
| lead_intake_exceptions | Stores exception information |
| Prepare CRM Failure | Creates failure response fields |
| Insert row | Writes an n8n Data Table record |
| Respond - CRM Success | Responds on a successful path |
| Respond to Webhook | General webhook response |
| Respond - CRM Failed | Returns failure information |

The export is a reusable starting point. Check that repeated lead submissions actually produce the intended deduplication result before claiming durable idempotency.
