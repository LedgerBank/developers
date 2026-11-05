# developers

API contracts, architecture and integration documentation.

**Status: presentation preview.** This repository contains scope and design documentation. It does not contain a released implementation or a live service.

## Role in the headless platform

LedgerBank is being organized around a common financial capability layer. Applications,
accounting workflows, SDKs, the CLI and agents are intended to consume that layer through
reviewed interfaces. Financial authority and permissions remain in the platform.

**Primary audience:** developers. **Repository visibility:** public.

## Planned scope

- Document the public headless API boundary and versioning policy.
- Define authentication, scopes, tenant context, pagination and errors.
- Describe sandbox scenarios, event contracts and integration recipes.
- Keep public documentation derived from a reviewed public contract.

## Read next

- [Scope and boundaries](docs/SCOPE.md)
- [First implementation acceptance criteria](docs/ACCEPTANCE.md)
- [Current repository status](STATUS.md)
- [developers](https://github.com/LedgerBank/developers) for the proposed public architecture and integration map

## Preview boundary

This is a new presentation scaffold. Existing repositories, branches, services and
documents have not been migrated here. Package names, hosted endpoints, releases and
support commitments will be documented only when they exist and have been verified.
