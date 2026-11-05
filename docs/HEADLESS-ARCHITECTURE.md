# Headless architecture: proposed public boundary

The headless layer is the product foundation. Interfaces for accountants, operators,
developers and agents consume financial capabilities through the same reviewed boundary.

| Layer | Intended responsibility | Authority |
|---|---|---|
| Domain and data | Financial state, posting invariants, permissions and approvals | Authoritative |
| API and events | Versioned capabilities, identity, request and event contracts | Delegated domain access |
| SDKs and CLI | Ergonomic clients, validation and diagnostics | No additional authority |
| MCP and product harness | Tool discovery, scoped runs, plans and evidence | Bounded by user capabilities |
| Accounting workflows | Workpapers, proposed entries, close and exception review | Preparation and review |
| Applications | Human interfaces and integration-specific experiences | Clients of the capability layer |

## Three intended end-to-end flows

1. An accountant requests reconciliation, receives matched items and exceptions, reviews
   supporting evidence, and separately authorizes any proposed posting.
2. A developer authenticates to a sandbox, calls a typed client, receives an event and
   diagnoses a failed delivery with a request identifier.
3. An agent prepares a payment request under the acting user's scopes, records its intent,
   obtains the required human approval, and observes the separately authorized outcome.

These are target flows. This preview does not expose an API or implement them.
