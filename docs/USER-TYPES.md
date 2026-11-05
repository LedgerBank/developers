# User types and access design

This catalog distinguishes personas from authorization roles. Documented-baseline labels refer to reviewed source documents or source code, not to a live permission audit. Proposed refinements are not active roles.

| User type | Group | Role mapping | Scope | Basis |
|---|---|---|---|---|
| Business owner | customer | owner | Ownership, company settings and policy | documented baseline |
| Business administrator | customer | admin | Team and company administration within policy | documented baseline |
| Finance manager | customer | finance | Books, bills, invoices, reconciliation and payment preparation | documented baseline |
| In-house bookkeeper | customer | finance | Daily coding, reconciliation, bills and invoice preparation | documented baseline persona |
| Independent approver | customer | approver | Approve authorized requests created by another actor | documented baseline |
| Employee / cardholder | customer | employee | Own cards, receipts, claims and permitted personal records | documented baseline |
| In-house accountant | customer | accountant | Books, reconciliation, documents and scoped accounting actions | documented baseline |
| Read-only stakeholder | customer | viewer | Permitted balances, activity and reports | documented baseline |
| Personal customer | customer | membership-specific | Own relationship and explicitly granted accounts | documented target flow |
| Joint account owner | customer | relationship-specific membership | Only jointly authorized accounts and relationship records | documented target relationship |
| Trustee / authorized fiduciary | customer | relationship-specific membership | Only authorized trust accounts and supported fiduciary actions | documented target relationship |
| Controller / accounting manager | customer | capability bundle to approve | Review journals, close periods and accounting exceptions | proposed refinement |
| Accounts payable specialist | customer | capability bundle to approve | Bills, matching and payment-request preparation | proposed refinement |
| Accounts receivable specialist | customer | capability bundle to approve | Invoices, receipts, matching and aging | proposed refinement |
| Treasury / CFO analyst | customer | capability bundle to approve | Cash positions, forecasts and reviewed funding requests | proposed refinement |
| Payroll administrator | customer | capability bundle to approve | Payroll preparation and own-domain review | documented target domain; role refinement |
| Wealth client | customer | product-specific membership | Own investment relationship, disclosures and permitted portfolio records | documented target domain |
| Credit applicant / borrower | customer | product-specific membership | Own applications, offers and permitted servicing records | documented target domain |
| Merchant operator | customer | product-specific capability bundle | Merchant acceptance, payout records and disputes within policy | documented target domain |
| Authorized wealth adviser | customer | professional capability bundle to approve | Assigned advisory relationships subject to professional and provider gates | proposed refinement of target domain |
| Accounting firm administrator | firm | firm role + engagement | Firm members and client assignments; no implicit client authority | documented baseline |
| Assigned firm accountant | firm | accountant intersection + engagement | Only assigned clients and engagement-granted accounting capabilities | documented baseline |
| Assigned firm bookkeeper | firm | firm role + engagement | Assigned-client preparation and reconciliation | documented baseline |
| Firm reviewer / engagement manager | firm | capability bundle + engagement | Review workpapers and accounting deliverables within an engagement | proposed refinement |
| External auditor / assurance reviewer | firm | auditor template + engagement | Time-bounded client evidence access; findings in a separate workspace | proposed engagement refinement |
| Audit engagement manager | firm | auditor template + engagement | Review audit workpapers and findings without client financial writes | proposed engagement refinement |
| Tax preparer | firm | credentialed capability + engagement | Prepare source-linked tax workpapers within scope | documented target flow; role refinement |
| Tax reviewer / authorized professional | firm | credentialed reviewer capability + engagement | Review and release professional deliverables under policy; no implicit filing | proposed refinement of target flow |
| Integration developer | technical | member + approved developer capabilities | Sandbox, contract and integration diagnostics | documented baseline |
| Customer integration service principal | technical | key or OAuth scopes | Only explicitly delegated organization capabilities | documented baseline |
| Accounting firm integration principal | technical | firm key + active engagement | Assigned-client data within both key and engagement scopes | documented baseline |
| Product financial agent | technical | sponsor + narrowed agent scopes | Run approved tools without acquiring independent approval authority | documented baseline |

## Access boundaries

- A person's job title does not itself grant a capability.
- Every action resolves acting identity, organization, account scope and current membership.
- A firm member also needs an active engagement and client assignment. Effective permissions
  are the intersection of firm authority, engagement scope and allowed client capabilities.
- The reviewed firm-access evaluator excludes money-out, approvals, card management,
  recipients, API-key administration, policy changes and user/role administration.
- Auditors may write findings in their own review workspace; their client financial access
  remains read-only. An internal auditor does not inherit a platform administrator's powers.
- Preparation, review, approval, execution and reconciliation are separate stages.
- A requester cannot approve their own request through another key, agent or interface.
- Service principals and agents have narrowed delegated scopes, not independent human roles.
- Technical infrastructure credentials are not product permissions.
- A reviewer may record tax-workpaper notes within scope; professional release additionally
  requires verified credentials and named release authority. Auditor status does not supply it.

No accounts, memberships, roles or permissions are changed by this design package.
