# developers: scope

- Document the public headless API boundary and versioning policy.
- Define authentication, scopes, tenant context, pagination and errors.
- Describe sandbox scenarios, event contracts and integration recipes.
- Keep public documentation derived from a reviewed public contract.

## Boundaries

Public interfaces must not expose provider credentials, internal operator surfaces, customer data or privileged configuration. Product agents use scoped capabilities; development-agent orchestration has a separate role.
