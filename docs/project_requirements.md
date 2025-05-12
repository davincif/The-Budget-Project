# Project Requirements

## Index

- [Project Requirements](#project-requirements)
  - [Index](#index)
  - [Glossary](#glossary)
  - [Features](#features)
    - [1. User Authentication](#1-user-authentication)
    - [2. Account Balance Management](#2-account-balance-management)
    - [3. Transfers Between Accounts](#3-transfers-between-accounts)
    - [4. Income Management](#4-income-management)
    - [5. Expense Management](#5-expense-management)
    - [6. Sporadic Income Features](#6-sporadic-income-features)
    - [7. Predict Monthly Budget](#7-predict-monthly-budget)
  - [Use Cases](#use-cases)
    - [Salary Income](#salary-income)
    - [Expense Examples](#expense-examples)
    - [Transfers \& Spillover](#transfers--spillover)
    - [Budget Monitoring](#budget-monitoring)
  - [FInal Considerations](#final-considerations)

## Glossary

| Term                 | Definition                                                                                                                                                  |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Accounting Cycle     | A defined period (usually a month) in which the user's financial activity is analyzed to extract insights and predictions.                                  |
| Account Balance      | A source of capital managed by the user (e.g., bank account, wallet, piggy bank).                                                                           |
| Disabled Account     | An Account Balance that is inactive due to historical transactions, and cannot be used for future transactions unless reactivated.                          |
| Transaction          | Any movement of capital within or across Account Balances. Includes expenses, income, and transfers.                                                        |
| Periodic Transaction | A scheduled transaction set to occur repeatedly over Accounting Cycles.                                                                                     |
| Income               | A positive Transaction where funds are added to an Account Balance.                                                                                         |
| Salary Income        | A recurring Income (usually monthly) representing the user's regular salary.                                                                                |
| Sporadic Income      | A one-time or irregular Income such as a bonus, refund, or sale.                                                                                            |
| Expense              | A negative Transaction representing spending or money leaving an Account Balance. (Also referred to as Outcome.)                                            |
| Transfer             | A Transaction that moves funds between two Account Balances.                                                                                                |
| Spill Over           | The financial data from one Accounting Cycle that influences or carries over into the next.                                                                 |
| Expression           | A formula-like reference (e.g., referencing other transactions) used to compute the value of a new Transaction. May be abstracted through the UI.           |
| Monthly Budget       | The predicted amount of money available for discretionary spending after accounting for all known incomes and expenses within the current Accounting Cycle. |

> _Note: All financial events (income, expense, transfer) are treated as Transactions with different categories._

## Features

### 1. User Authentication

- Login with username or email + password
- Logout
- Password recovery functionality

### 2. Account Balance Management

- Create and name new Account Balances
- View list of Account Balances with descriptions and current balance
- Delete Account Balances
  - If the account has transaction history, it is marked as disabled (not deletable)
  - If no history, it can be deleted completely
- View and reactivate Disabled Accounts

### 3. Transfers Between Accounts

- Transfer funds between two Account Balances.
  - Specify title, description, amount, and date
- View transfers per Accounting Cycle and per Account Balance

### 4. Income Management

- Add Salary Income or Sporadic Income to an Account Balance

  - Fields: name, description, amount, date, recurrence
  - System auto-generates a CreatedAt timestamp

- Edit, delete, or copy existing incomes
- Schedule recurring Salary Income
  - Define start/end dates or set it to unlimited recurrence
- Use Expressions to define income values

### 5. Expense Management

- Add Expenses (Outcomes) to an Account Balance

  - Same data fields as Income

- Support Periodic and Repeatable Expenses
- Use Expressions to define expense values
- Edit, delete, or copy past expenses

### 6. Sporadic Income Features

- Represent unexpected income (e.g., refund from a group bill)
- Link a Sporadic Income to a related Expense for net balance prediction

### 7. Predict Monthly Budget

- After adding all expected incomes and expenses, the user should:

  - View the predicted Monthly Budget (free-to-spend amount)
  - Understand how each transaction impacts their discretionary budget
  - To know how much of his current balance is due to a Net Balance from last Cycle

## Use Cases

### Salary Income

- User receives regular monthly salary — should be able to schedule it.
- User gets vacation bonus — can calculate it via Expression (e.g., 1/3 of salary).

### Expense Examples

- Taxi to the hospital (single, unexpected expense)
- Monthly energy bill (repeatable expense)
- Grocery budgeting (planned via partial Payments or Expressions)
- Medical follow-up appointment (copy a past transaction)

### Transfers & Spillover

- Money shifted between two accounts should reflect as Transfers
- Unused budget or debts from past cycles should carry forward as Spill Over

### Budget Monitoring

- After all data is entered, display a clear monthly prediction:

  - Total expected income
  - Total planned expenses
  - Net monthly balance (budget to spend)

## FInal Considerations

> This document is a living specification and subject to improvements as the project evolves. Contributions and clarifications are welcome!
