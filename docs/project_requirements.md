# Project Requirements

## Index

_NOT IMPLEMENTED_

## Glossary

| Term               | Meaning                                                                                                              |
| ------------------ | -------------------------------------------------------------------------------------------------------------------- |
| Accounting Cycle   | The month were a certain accouting is happening from who we extract useful predictions.                              |
| Account Balance    | A source of capital managed by the user. It can be a bank accout, a wallet, a piggy bank... whatever the user wants. |
| Disabled Accounts  | An _Account Balance_ that can no loger be used.                                                                      |
| Account Transation | A capital movement in an _Account Balance_.                                                                          |
| Income             | A positve _Account Transation_, representing some capital the user recieved/added to an _Account Balance_.           |
| Outcome            | The negative of _Income_, representing any expenses a user might have.                                               |
| Transference       | An _Account Transatoin_ between _Account Balances_.                                                                  |

## Features

1. Autentication
   1. Login
   1. Logout
   1. Password Recovery
1. Manage Account Balance
1. Manage Transferece

## Autentication

The must me able to login through, user name or email, and password.

## Manage Account Balance

The user must be able to create an _Account Balance_ from which he can add or remove capital (income and outcome).

Features:

1. A page where the user can visualise his accounts, theirs descriptions and balences.
1. The user must be able to **create** or delete an Account Balance. Giving to it:
   1. name
   1. description
   1. An Account Balance is always created with 0 (capital) in it.
1. The balance of an account can only change throw some _Account Transation_.
1. The user must be able to delete an _Account Balance_
   1. If there's ANY prior _Account Transation_ made with this account:
      1. It must be only "disabled", meaning that not other _Account Transation_ can ever occur again for this _Account Balance_, the user must recieve an visitual indication of that whenever we crosses that _Account Balance_ again.
   1. If there's NO prior _Account Transation_ made with this account:
      1. It can be completely deleted.
1. The user must have a page where he can see the _Disabled Accounts_ and reactivate them.

## Transferece

The user must be able to transfer capital in between _Account Balances_.

Features:

1. The user must be able to visualise all the _Transference_ in the _Cicly_.
1. The user must be able to visualise all the _Transference_ of an _Account Balance_. - **Desirable Feature**
1. The user must be able to create a _Transference_ of capital in between two _Account Balances_, informaing: a title, a description and a date for when it happened.
