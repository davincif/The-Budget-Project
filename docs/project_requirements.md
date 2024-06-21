# Project Requirements

## Index

_NOT IMPLEMENTED_

## Glossary

| Term               | Meaning                                                                                                                          |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| Accounting Cycle   | The month were a certain accouting is happening from who we extract useful predictions.                                          |
| Account Balance    | A source of capital managed by the user. It can be a bank accout, a wallet, a piggy bank... whatever the user wants.             |
| Disabled Accounts  | An _Account Balance_ that can no loger be used.                                                                                  |
| Account Transation | A capital movement in an _Account Balance_.                                                                                      |
| Projection\*       | An _Account Transation_ that did not happen just yet                                                                             |
| Income             | A positve _Account Transation_, representing some capital the user recieved/added to an _Account Balance_.                       |
| Salary Income\*    | An _Income_ of greate importance, like the user's montly salary, or a bonous his just recieved.                                  |
| Sporadic Income\*  | Some ponctual _Income_ from the External World that will likelly not happen again, like a loan return the user made to a friend. |
| Outcome            | The negative of _Income_, representing any expenses a user might have.                                                           |
| Transference       | An _Account Transatoin_ between _Account Balances_.                                                                              |
| Spill Over         |                                                                                                                                  |

\* needs better thinking

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

~ The user must be able to ~

1. Visualise all the _Transference_ in the _Cicly_.
1. Visualise all the _Transference_ of an _Account Balance_. - **Desirable Feature**
1. Create a _Transference_ of capital in between two _Account Balances_, informaing: a title, a description and a date for when it happened.

## Salary Income

The user must be able to create an _Account Transation_ in a _Account Balance_ in order to represent some new capital that got added from the external world to the users _Accounting Cycle_.

Features:

~ The user must be able to ~

1. Easily visualize such incomes, for great is it's importance.
1. Create _Salary Incomes_ to an _Account Balance_.
   1. The user may create an _Salary Incomes_ as a _Projection_.
   1. Add a _Projection_ for only a certain amount of _Accounting Cycle_.
   1. If the _Salary Incomes_ is a _Projection_, the user can apply the _Transation_ to the _Account Balance_ at any time we wants.
   1. To make an _Salary Incomes_ repeatable every _Accounting Cycle_ as _Projctions_.
   1. To make an _Salary Incomes_ not repeatable anymore from a certain _Accounting Cycle_.
   1. The repeatable _Projections_ might occour for an unlimeted or limited amount of _Accounting Cycles_.
1. Remove an _Salary Incomes_
   1. When removing an _Salary Incomes_ that has _Projections_, the user must choose beteween deleting only the current _Salary Incomes_ or all the _Projection_ with it.
1. Edit a _Salary Incomes_.

PS.: _Salary Incomes_ _Projections_ are a just **Desirable Feature**.

PS².: It's up for debate if, maybe, a copy functionality would be enough instead of the Projectoins.

## Outcomes

The user must be able to create an _Account Transation_ from a _Account Balance_ to te external world that represents an expese that he had during his _Accounting Cycle_.

Features:

~ The user must be able to ~

1. Easily visualize all outcomes in the _Accounting Cycle_.
1. Create an _Outcome_ representing an expese the user had.
1. Remove an _Outcome_.
1. Edit an _Outcome_.
1. Create an _Outcome_ as a _Projection_, that is, not yet paid.
   1. Pay the yet not paied _Projected_ _Outcome_.
1. Create an repeatable _Outcome_ — just like _Salary Income_.
<!-- 1. ciar gasto com parâmetro e expressão -->
