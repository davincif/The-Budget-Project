# Project Requirements

## Index

_NOT IMPLEMENTED_

## Glossary

| Term                   | Meaning                                                                                                                                           |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Accounting Cycle       | The month were a certain accouting is happening from who we extract useful predictions.                                                           |
| Account Balance        | A source of capital managed by the user. It can be a bank accout, a wallet, a piggy bank... whatever the user wants.                              |
| Disabled Accounts      | An _Account Balance_ that can no loger be used.                                                                                                   |
| Account Transation     | A capital movement in an _Account Balance_.                                                                                                       |
| Projection\*           | An _Account Transation_ that did not happen just yet                                                                                              |
| Income                 | A positve _Account Transation_, representing some capital the user recieved/added to an _Account Balance_.                                        |
| Salary Income\*        | An _Income_ of greate importance, like the user's montly salary, or a bonous his just recieved.                                                   |
| Sporadic Income\*      | Some ponctual _Income_ from the External World that will likelly not happen again, like a loan return the user made to a friend.                  |
| Outcome                | The negative of _Income_, representing any expenses a user might have.                                                                            |
| Transference           | An _Account Transatoin_ between _Account Balances_.                                                                                               |
| Spill Over\*           | Everything that needs to be taken into consideration from one _Accounting Cycle_ to the other.                                                    |
| Expression¹            | Like in a Exel SpreadSheet, the capital of a _Account Transation_ can be defined by references to other Transations and mathematical expressions. |
| Predicted Free Balance | The amount of capital that, all _Incomes_ and _Outcomes_ considered, is free for the user to freely expense in the _Accounting Cycle_.            |

\* needs better thinking

OBS¹: Although the desired effect of an Expression, might be achieved by writing a mathematical formula; it doest has to! It's important to notice that the same effect can be reached by clever UX; Even if, under the hood, we use expressions anyways to perform the actual work.

## Features

1. [Autentication](#Autentication)
   1. Login
   1. Logout
   1. Password Recovery
1. [Manage Account Balances](#Manage-Account-Balance)
1. [Manage Transfereces](#Transferece)
1. [Manage Salary Incomes](#Salary-Income)
1. [Manage Outcomes](#Outcomes)
1. [Manage Sporadic Incomes](#Sporadic-Income)
1. [Predict Free Balance](#Predict-Free-Balance)

<a name="Autentication"></a>

## Autentication

The must me able to login through, user name or email, and password.

<a name="Manage-Account-Balance"></a>

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

<a name="Transferece"></a>

## Transferece

The user must be able to transfer capital in between _Account Balances_.

Features:

**~ The user must be able to ~**

1. Visualise all the _Transference_ in the _Cycle_.
1. Visualise all the _Transference_ of an _Account Balance_. — **Desirable Feature**
1. Create a _Transference_ of capital in between two _Account Balances_, informaing: a title, a description and a date for when it happened.

<a name="Salary-Income"></a>

## Salary Income

The user must be able to create an _Account Transation_ in a _Account Balance_ in order to represent some new capital that got added from the external world to the users _Accounting Cycle_.

When creating an Income the user must:

1. Provide a name for it, it's description and capital.
1. Provide at wich _Account Balance_ the _Transaction_ must take effect in — Option if a _Projeciton_.
1. Optionally, the date when it was made, or a date when it will be made (in case it's a projection).
1. And the system should automatically register the date this _Income_ was inserted in the system.

**~ The user must be able to ~**

1. Easily visualize such incomes, for great is it's importance.
1. Edit a _Salary Incomes_.
1. Remove an _Salary Incomes_.
1. A _Salary Incomes_ can be copied just like an _Outcome_.

---

#### Use case 01 — My Hard-Earned Money

After a whole month of hard work, the user owns one or two pay checks with his rightfully hard-earned money. He needs to keep track of that.

**~ Therefore, the user must be able to ~**

1. Create _Salary Incomes_ to an _Account Balance_.

---

#### Use case 02 — Vocation Bonus! \o/

After a hole year of hard work the user will recieve an extra money from his company in order to better enjoy his time out. Hooraaay! The value he'll recieve is 1/3 of his Salary (which he had already inserted in the system).

**~ Therefore, the user must be able to ~**

1. Create _Salary Incomes_ whose capital is an _Expressoin_ in order to refer to an already existing _Income_ and add some mathematical expression to it.

---

#### Use case 03 — It's Monthly My Salary

After a hole year in the same company, recieving almost the same salary, the user would like to not have to wast time adding the same information to te system over and over again every month.

**~ Therefore, the user must be able to ~**

1. The user may create an _Salary Incomes_ as a _Projection_.
1. Add a _Projection_ for only a certain amount of _Accounting Cycle_.
1. If the _Salary Incomes_ is a _Projection_, the user can apply the _Transation_ to the _Account Balance_ at any time we wants in the future, but still within the _Accounting Cycle_.
1. To make an _Salary Incomes_ repeatable every _Accounting Cycle_ as _Projctions_.
1. To make an _Salary Incomes_ not repeatable anymore from a certain _Accounting Cycle_.
1. The repeatable _Projections_ might occour for an unlimeted or limited amount of _Accounting Cycles_.
1. When removing an _Salary Incomes_ that has _Projections_, the user must choose beteween deleting only the current _Salary Incomes_ or all the _Projection_ with it.

PS².: It's up for debate if, maybe, a copy functionality would be enough instead of the Projectoins. Also, perhaps both funcionality should exist.

<a name="Outcomes"></a>

## Outcomes

The user must be able to create an _Account Transation_ from a _Account Balance_ to the external world that represents an expese that he had during his _Accounting Cycle_.

When creating a Outcome, the user must provide the same information of the Income.

**~ The user must be able to ~**

1. Easily visualize all _Outcomes_ in the _Accounting Cycle_.
1. Remove an _Outcome_.
1. Edit an _Outcome_.

---

#### Use case 01 — The Taxy Bill

The user had a belly ache and needed to go to the hospital. To do that fast, we got a taxy. Now he needs to register this expense.

**~ Thefore, the user must be able to ~**

1. Create an _Outcome_ representing an expese the user had, with imediate inpact on a _Account Balance_.

---

#### Use case 02 — The Power Bill

The user just recieved is power bill and the price was a bad surprise. Now, he wants to prevent this by adding in his current mounth expenses, a.k.a _Accounting Cycle_, a _Projection_ for the next _Accounting Cycle_ power expense.

**~ Thefore, the user must be able to ~**

1. Create an _Outcome_ as a _Projection_, that is, not yet paid.
   1. Pay the yet not paied _Projected_ _Outcome_.
1. Create an repeatable _Outcome_ — just like in _Salary Income_.

---

#### Use case 03 — The Grocery

**Story 1** — In the end of his _Accounting Cycle_, the user noticed we expend too much on other things and there were not enough money for grocery in the last week of the month. If only he could have reserved the correct about of money beforehand, that could have been avoided.

**Story 2** — By the end of an _Accounting Cycle_, the user just noticed he expended way too much money only on his recurrent groceries. He knew he should not have brought all that junk food! If only we could track his expenses on groceries to see if it's reaching his mountgly budget...

**~ Thefore, the user must be able to ~**

1. Create _Outcome_ whose capital is an _Expressoin_ in order to make partial payment of this _Projection_.

---

#### Use case 04 — I need a Medical Appointment Again

**Story 1** — In a cold day of winter, the users toddler woke up with a burning feaver; He immediatly took her to the a doctor and took note of the appointment expense in the system. She got better, but one week down the line, but already in the next month, the medical scenario worsened again, and te user had to take her back to the same medical appointment.

The user would like to copy all the expense's information from the last medical appointment since it's going to be exactly the same, only, maybe, with a different value.

**Story 2** — The user had just came back to his Psicological appointment; but he already had one last week, still in this same month, and had added this expense to the system. We would like to copy the same expense from before since they are equal.

**~ Thefore, the user must be able to ~**

1. Create a new _Outcome_ by selecting and coping another one form inside or outside the current _Accounting Cycle_.

<a name="Sporadic-Income"></a>

## Sporadic Income

The user may be able to create incomes that are sporadic,taking effect in an _Account Balance_; that would represent some unexpected or not very important income that users just recieved, like a some money that a colleague gave you to pay his share on the pizza time.

When creating a Outcome, the user must provide the same information of the Income and Outcome.

**~ The user must be able to ~**

1. Easily visualize all _Sporadic Income_ in the _Accounting Cycle_ together with the _Outcomes_.
1. Remove a _Sporadic Income_.
1. Edit a _Sporadic Income_.

---

#### Use case 01 — Helping a Relative Out

**Story 1** — On a bright summer day, the users recieved a call from his ant. She was in need of some money to go to the doctor, she had no money at the time and asked her son to loan her the money. She's a woman of her word and promissed her simbling that she would give the money back as soon as her wage droped. The user wants to borrow the money, but he doesn't wan't to affect his _Predicted Free Balance_.

**Story 2** — On a happy sunday, the user went out for a bar with some friends. From tere they decided to go somewhere else, and to make it quick the user paid the whole bill and his friend would refound him late in anoter day. The user wanted to add this _Transferece_ that occoured in his _Account Balance_ without compromissing his _Predicted Free Balance_.

**~ Thefore, the user must be able to ~**

1. Add create a _Sporadic Income_ related with an _Outcome_. — Perhaps by throw the expressions?
1. Create multiple _Sporadic Income_ related to a single _Outcome_.

<a name="Predict-Free-Balance"></a>

## Predict Free Balance

The Final object of this project is to give the user a very good idea of how much he can expend in his mounth witout hurting his financial life. For that we need to have a clear view of this number.

---

#### Use case 01 — Keep me on the track

After adding all his income, money already existent in his accounts, and all his projected expenses for the month, like water and power bills; the user now wantes to see how much money is free for him and that he can safely expend.

**~ Thefore, the user must be able to ~**

1. Visualize, clearly and easily, the projected free capital for the current _Accounting Cycle_.
