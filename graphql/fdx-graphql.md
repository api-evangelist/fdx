---
name: FDX GraphQL Schema
description: Conceptual GraphQL schema for the Financial Data Exchange (FDX) open finance standard. Models the full FDX API v6.5 domain covering deposit, loan, credit, investment, line-of-credit, insurance, and annuity accounts; transactions; investment positions; statements; rewards; transfers; customer identity; consent management; and the OAuth2/FAPI/PAR authorization layer used by FDX-compliant data providers and data recipients.
tags:
  - FDX
  - Financial Data Exchange
  - Open Finance
  - Open Banking
  - GraphQL
  - Accounts
  - Transactions
  - Investments
  - Consent
  - OAuth2
  - FAPI
  - CFPB 1033
---

# FDX GraphQL Schema

## Overview

This GraphQL schema provides a conceptual representation of the [FDX API v6.5](https://financialdataexchange.org) standard produced by Financial Data Exchange (FDX). FDX is a non-profit industry standards body whose royalty-free REST specification governs consumer-permissioned financial data sharing in the United States and Canada. As of 2026, over 130 million consumer accounts are connected via the FDX API across 200+ member organizations.

The schema in `fdx-schema.graphql` translates the FDX REST resource model into a typed GraphQL surface, enabling query-driven access to the same data clusters defined in the FDX specification: accounts, transactions, investments, insurance, tax data, payroll, consent, and identity.

## Schema File

`fdx-schema.graphql`

## Type Coverage

### Account Domain

| Type | Description |
|---|---|
| `Account` | Interface shared by all account varieties |
| `AccountDetails` | Shared metadata returned for any account |
| `AccountType` | Enum: DEPOSIT, LOAN, CREDIT, INVESTMENT, LOC, INSURANCE, ANNUITY, OTHER |
| `AccountStatus` | Enum: OPEN, CLOSED, PENDING_OPEN, PENDING_CLOSE, RESTRICTED, DELINQUENT |
| `DepositAccount` | Demand deposit and savings account with balance, APY, and transactions |
| `LoanAccount` | Consumer or commercial loan with principal, payments, and maturity |
| `CreditAccount` | Revolving credit card account with limit, rewards, and statements |
| `InvestmentAccount` | Brokerage or retirement account with holdings and positions |
| `LocAccount` | Revolving line of credit account |
| `InsuranceAccount` | Insurance policy account with coverage, premium, and beneficiaries |
| `AnnuityAccount` | Deferred annuity account with surrender and accumulated values |

### Balance Domain

| Type | Description |
|---|---|
| `Balance` | Point-in-time balance amount with currency and type |
| `AccountBalance` | Full FDX balance record including current, available, and opening-day amounts |
| `BalanceDate` | Timestamp and precision qualifier for a balance observation |

### Transaction Domain

| Type | Description |
|---|---|
| `Transaction` | Posted or pending financial transaction |
| `TransactionDetails` | Extended reference, payee, and merchant attributes |
| `TransactionType` | Enum: CREDIT, DEBIT, DIVIDEND, FEE, INTEREST, PAYMENT, PURCHASE, REFUND, TRANSFER, WITHDRAWAL, OTHER |
| `TransactionStatus` | Enum: PENDING, POSTED, MEMO, VOID, OTHER |
| `MerchantDetails` | Merchant name, MCC, ID, and location |
| `PaymentDetails` | Loan payment breakdown: principal, interest, escrow |

### Transfer Domain

| Type | Description |
|---|---|
| `Transfer` | A fund transfer between accounts |
| `TransferDetails` | Structured transfer request and response attributes |

### Rewards Domain

| Type | Description |
|---|---|
| `Reward` | A reward program record attached to a credit account |
| `RewardDetails` | Points or cash-back balance, rate, unit, and expiry |

### Investment Domain

| Type | Description |
|---|---|
| `Investment` | Summary investment record within a portfolio |
| `InvestmentTransaction` | Buy, sell, dividend, or other investment-specific transaction |
| `InvestmentPosition` | Current position with market value, cost basis, and gain/loss |
| `Security` | Reference to a financial security |
| `SecurityDetails` | Ticker, CUSIP, ISIN, type, exchange, and issuer metadata |
| `SecurityType` | Enum: STOCK, MUTUAL_FUND, ETF, BOND, OPTION, FUTURE, CASH, OTHER |
| `HoldingDetails` | Holding summary linking account, security, and valuation |

### Statement Domain

| Type | Description |
|---|---|
| `Statement` | A periodic account statement with document URL |
| `StatementDetails` | Opening/closing balances, totals, and creation date |
| `StatementPeriod` | Start and end dates covered by a statement |

### Customer and Identity Domain

| Type | Description |
|---|---|
| `Customer` | Consumer or business customer of a financial institution |
| `CustomerDetails` | Name, contact, address, and tax ID for a customer |
| `CustomerIdentity` | Verified identity attributes and KYC result |
| `Address` | Physical or mailing address |
| `IdentityDetails` | An identity document used for verification |
| `Identity` | OpenID Connect identity with claims |
| `KYC` | Know Your Customer compliance record with risk level and AML flags |

### Consent Domain

| Type | Description |
|---|---|
| `Consent` | A consumer consent grant under the FDX Consent API |
| `ConsentDetails` | Full consent attributes including scopes, accounts, and purpose |
| `ConsentScope` | Enum: ACCOUNT_BASIC, ACCOUNT_DETAILED, TRANSACTIONS, INVESTMENTS, INSURANCE, TAX_DATA, PAYROLL, STATEMENTS, CUSTOMER_INFO, IDENTITY |
| `ConsentExpiry` | Expiry timestamp, duration, and legal basis for a consent grant |
| `ConsentStatus` | Enum: ACTIVE, REVOKED, EXPIRED, PENDING |

### Authorization Domain (OAuth2 / FAPI / PAR)

| Type | Description |
|---|---|
| `Token` | Issued token set linking OAuth2 tokens to a consent and customer |
| `OAuthToken` | OAuth2 bearer token response: access token, refresh token, scope, id token |
| `PushedAuthorization` | PAR response with request_uri and expiry |
| `PKCE` | PKCE code challenge / verifier pair for FAPI-compliant flows |
| `OAuth2` | Authorization server metadata and supported capabilities |
| `PAR` | Pushed Authorization Request reference record |
| `Claims` | OpenID Connect claims payload |

### Registration Domain

| Type | Description |
|---|---|
| `Registration` | OAuth2 dynamic client registration record |
| `ClientDetails` | Registered client attributes: URIs, scopes, JWKS, software ID |
| `APIKey` | API key credential with scope, status, and expiry |

### Pagination and Utility Types

| Type | Description |
|---|---|
| `PageInfo` | Relay-style cursor pagination metadata |
| `AccountConnection` / `AccountEdge` | Paginated account list |
| `TransactionConnection` / `TransactionEdge` | Paginated transaction list |
| `InvestmentTransactionConnection` / `InvestmentTransactionEdge` | Paginated investment transaction list |
| `StatementConnection` / `StatementEdge` | Paginated statement list |
| `CustomerConnection` / `CustomerEdge` | Paginated customer list |
| `ConsentConnection` / `ConsentEdge` | Paginated consent list |
| `FinancialInstitution` | Top-level FI node with accounts and customers |
| `FIDetails` | FI metadata: routing number, SWIFT, FDX member ID, API version |
| `FIAttribute` | Arbitrary FI-defined name/value attribute for extensibility |
| `KeyValuePair` | Generic extensibility pair |
| `Link` | Hypermedia link with rel, href, and method |

## Root Operations

### Query

- `financialInstitution(fiId)` - Retrieve a financial institution by ID
- `accounts(accountType, status, first, after)` - List accessible accounts under current consent
- `account(accountId)` - Retrieve detail for a single account
- `accountBalance(accountId)` - Retrieve balance for a single account
- `transactions(accountId, startDate, endDate, transactionType, status, first, after)` - Retrieve transactions
- `transaction(accountId, transactionId)` - Retrieve a single transaction
- `investmentPositions(accountId)` - Retrieve investment positions
- `investmentTransactions(accountId, startDate, endDate, first, after)` - Retrieve investment transactions
- `statements(accountId, first, after)` - Retrieve statements
- `statement(accountId, statementId)` - Retrieve a single statement
- `customer(customerId)` - Retrieve customer details
- `customers(first, after)` - List customers under current token
- `customerIdentity(customerId)` - Retrieve verified identity
- `consents(customerId, status, first, after)` - List consent records
- `consent(consentId)` - Retrieve a single consent
- `security(securityId)` - Retrieve a security by ID
- `rewards(accountId)` - Retrieve reward program details
- `oauth2Metadata` - Retrieve authorization server metadata
- `registration(clientId)` - Retrieve a registered client
- `apiKey(keyId)` - Retrieve an API key record

### Mutation

- `initiateTransfer(...)` - Submit a fund transfer
- `grantConsent(...)` - Grant a new consent for specified scopes
- `revokeConsent(consentId, reason)` - Revoke an active consent
- `updateConsentScopes(consentId, scopes)` - Modify scopes on an existing consent
- `registerClient(...)` - Register a new OAuth2 client (data recipient)
- `pushedAuthorizationRequest(...)` - Submit a PAR and receive request_uri

## FDX Standard References

- FDX API Specification: https://financialdataexchange.org
- Developer Portal: https://developer.financialdataexchange.org
- FDX Registry: https://registry.financialdataexchange.org
- GitHub (core-exchange reference): https://github.com/plaid/core-exchange
- CFPB Section 1033 Rule: https://www.consumerfinance.gov/rules-policy/final-rules/personal-financial-data-rights/
