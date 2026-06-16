# Financial Data Exchange (FDX) (fdx)

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
