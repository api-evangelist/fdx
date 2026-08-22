# Financial Data Exchange (FDX) (fdx)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Financial Data Exchange (FDX) is a non-profit industry standards body operating in the US and Canada that produces the FDX API, a royalty-free REST standard for consumer-permissioned financial data sharing. The FDX API defines interoperable endpoints covering deposit accounts, loan accounts, investment accounts, insurance policies, tax data, payroll data, reward programs, and consent management, enabling data providers (financial institutions), data access platforms (aggregators), and data recipients (fintechs) to exchange consumer financial data without exposing user credentials. As of early 2026 over 130 million consumer accounts are connected via the FDX API across 200+ member organizations including Bank of America, Chase, Citi, Wells Fargo, Plaid, and MX. FDX API v6.5 is the current stable release.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/fdx/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/fdx/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Financial Data
- Open Banking
- Open Finance
- Financial Data Exchange
- Consumer Permissioned
- Account Data
- Transactions
- Investments
- Insurance
- Tax Data
- Payroll
- REST
- OAuth2
- FAPI
- CFPB 1033

## Timestamps

- **Created:** 2026-06-13
- **Modified:** 2026-06-13

## APIs

### FDX Accounts API

RESTful endpoints for retrieving consumer deposit, loan, investment, and insurance account details including account numbers, balances, account holder identity, and account metadata. Supports the full FDX account data cluster across all account types recognized by the standard.

- **Human URL:** [https://financialdataexchange.org](https://financialdataexchange.org)
- **Base URL:** `https://api.financialdataexchange.org`

#### Tags

- Accounts
- Deposit Accounts
- Loan Accounts
- Account Balances
- Account Holder

#### Properties

- [Documentation](https://financialdataexchange.org)
- [OpenAPI](https://github.com/plaid/core-exchange) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Graph Q L](graphql/fdx-graphql.md)

### FDX Transactions API

RESTful endpoints for retrieving consumer transaction histories including pending and posted transactions, transaction categorization, merchant data, and transaction amounts across deposit, loan, and investment accounts within the permissioned scope.

- **Human URL:** [https://financialdataexchange.org](https://financialdataexchange.org)
- **Base URL:** `https://api.financialdataexchange.org`

#### Tags

- Transactions
- Transaction History
- Pending Transactions
- Merchant Data

#### Properties

- [Documentation](https://financialdataexchange.org)

### FDX Investment API

RESTful endpoints for retrieving investment account data including holdings, positions, investment transactions, cost basis, and portfolio composition. Covers brokerage, retirement, and managed investment accounts under the FDX investment data cluster.

- **Human URL:** [https://financialdataexchange.org](https://financialdataexchange.org)
- **Base URL:** `https://api.financialdataexchange.org`

#### Tags

- Investments
- Holdings
- Portfolio
- Brokerage
- Retirement

#### Properties

- [Documentation](https://financialdataexchange.org)

### FDX Insurance API

RESTful endpoints for retrieving insurance policy information including policy coverage details, premium schedules, claims history, and beneficiary data under the FDX insurance data cluster.

- **Human URL:** [https://financialdataexchange.org](https://financialdataexchange.org)
- **Base URL:** `https://api.financialdataexchange.org`

#### Tags

- Insurance
- Policy
- Coverage
- Claims

#### Properties

- [Documentation](https://financialdataexchange.org)

### FDX Tax API

RESTful endpoints for retrieving consumer tax data including tax document metadata and structured tax form data (1099s, W-2s, and related forms) as defined by the FDX US Tax Data specification and the CSDF Consensus Standard Data Format.

- **Human URL:** [https://financialdataexchange.org](https://financialdataexchange.org)
- **Base URL:** `https://api.financialdataexchange.org`

#### Tags

- Tax Data
- 1099
- W-2
- Tax Documents

#### Properties

- [Documentation](https://financialdataexchange.org)

### FDX Payroll API

RESTful endpoints introduced in FDX API v6.0 for retrieving permissioned payroll data including employment records, pay stubs, income verification, and direct deposit details, supporting lending and personal financial management use cases.

- **Human URL:** [https://financialdataexchange.org](https://financialdataexchange.org)
- **Base URL:** `https://api.financialdataexchange.org`

#### Tags

- Payroll
- Income Verification
- Employment
- Pay Stubs

#### Properties

- [Documentation](https://financialdataexchange.org)

### FDX Consent API

RESTful endpoints implementing the FDX Consent API Behavioral Specification for managing user permissions and consent events. Enables data recipients to initiate consent, query active consent grants, update scope, and handle consent revocation in compliance with CFPB Section 1033 requirements.

- **Human URL:** [https://financialdataexchange.org](https://financialdataexchange.org)
- **Base URL:** `https://api.financialdataexchange.org`

#### Tags

- Consent Management
- Authorization
- CFPB 1033
- Data Access
- Permissioning

#### Properties

- [Documentation](https://financialdataexchange.org)

## Common Properties

- [Website](https://financialdataexchange.org)
- [Documentation](https://financialdataexchange.org)
- [Developer Portal](https://developer.financialdataexchange.org)
- [Onboarding Portal](https://onboarding.financialdataexchange.org)
- [Registry](https://registry.financialdataexchange.org)
- [Blog](https://financialdataexchange.org/fdx-feed/)
- [Membership](https://financialdataexchange.org/about-fdx/)
- [Git Hub Org](https://github.com/plaid/core-exchange)
- [LinkedIn](https://www.linkedin.com/company/financialdataexchange)
- [X (Twitter)](https://x.com/fdxapi)
- [YouTube](https://www.youtube.com/@financialdataexchange)
- [Privacy Policy](https://financialdataexchange.org/privacy-policy/)
- [Terms of Service](https://financialdataexchange.org/terms-of-use/)
- [License Agreement](https://financialdataexchange.org/fdx-api-license-agreement/)
- [Authentication](https://financialdataexchange.org)
- [Plans](plans/fdx-plans-pricing.yml)
- [Rate Limits](rate-limits/fdx-rate-limits.yml)
- [Fin Ops](finops/fdx-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
