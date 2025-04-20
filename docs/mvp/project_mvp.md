# Project Requirements

## Index

_NOT IMPLEMENTED_

## Glossary

Doubts:
- Projection == Budget?

| Term        | Meaning                                                            |
|-------------|--------------------------------------------------------------------|
| Transaction | A financial transaction meaning being negative or positive balance |
| User        | The holder of an account                                           |
| Account     | The accumulated of transactions (Income and Expense)               |

## Entity's

### Transaction

- ID
- Name
- Description
- Amount
- Category
- CreatedAt
- UpdatedAt
- ExecutionDate
- isConfirmed
- isRecurrent
- recurrencyType
- recurrencyEnd
- TransactionReference
- RelatedAccount

### User

- ID
- Email
- Password
- CreatedAt
- UpdatedAt
- isActive

### Account

- ID
- Name
- Description
- Type (Enum)
- ExpectedAmount
- ConfirmedAmount
- AmountLastUpdated
- isActive
- UpdatedAt
- CreatedAt

## Future features

[ ] - NetGrowth;

[ ] - Relate transactions (Splitting, percentage, refundOfWhat);

[ ] - Build an expected calendar;