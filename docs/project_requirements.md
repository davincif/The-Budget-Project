# Project Requirements

## Index

_NOT IMPLEMENTED_

## Glossary

Doubts:
- Projection == Budget?

| Term                   | Meaning                                                                                                                                                  |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Accounting Cycle       | The period of time where a certain where we extract useful predictions.                                                                                  |
| Account Balance        | A source of capital managed by the user. (bank accout, wallet, piggy bank).                                                                              |
| Disabled Accounts      | An _Account Balance_ that can no loger be used.                                                                                                          |
| Transaction             | A capital movement in an _Account Balance_.                                                                                                             |
| Periodic Transaction\* | A _Transaction_ that did not happen just yet                                                                                                             |
| Income                 | A positve _Transaction_, representing the amount the user recieved/added to an _Account Balance_.                                                        |
| Salary Income\*        | A periodic _Income_, (user's montly salary).                                                                                                             |
| Sporadic Income\*      | A ponctual _Income_ not expected to happen again, (refund, bonus, split payment, sale, lottery...).                                                      |
| Outcome                | The negative of _Income_, representing any expenses a user might have.    **Same as Transaction?**                                                       |
| Transference           | An _Account Transaction_ between _Account Balances_. **Same as Transaction?**                                                                            |
| Spill Over\*           | Everything that needs to be taken into consideration from one _Accounting Cycle_ to the other. **Didnt understand**                                      |
| Expression¹            | Like in a Exel SpreadSheet, the capital of a _Transaction_ can be defined by references to other Transactions and mathematical expressions.**Forumulas?**|
| Month Budget           | The amount of capital that, after all _Incomes_ and _Outcomes_, available to use and expend in this _Accounting Cycle_.                                  |

\* needs better thinking

OBS¹: Although the desired effect of an Expression might be achieved by writing a mathematical formula; it does't need to! It's important to notice that the same effect can be reached by clever UX; Even if, under the hood, we use expressions anyways to perform the actual work.
OBS²: Everything should be considered Transaction but as different categories (Income, Expense, Periodic ...)

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

1. A page where the user can visualise his accounts, theirs descriptions and balances.
1. The user must be able to **create** or **delete** an Account Balance. Giving to it:
   1. name
   1. description
   1. An Account Balance is always created with 0 (capital) in it.
1. The balance of an Account can only change through a _Transaction_.
1. The user must be able to delete an _Account Balance_
   1. If there's **ANY** _Transaction_ history in this account:
      1. It must be "disabled", meaning that no other _Transaction_ can be made within this _Account Balance_, the user must recieve an visitual indication (alert) of that whenever he try to transfer to that _Account Balance_.
   1. If there's **NO** _Transaction_ history in this account:
      1. It can be completely deleted.
1. The user must have a page where he can see all his _Disabled Accounts_ and reactivate them if needed.

<a name="Transference"></a>

## Transference

The user must be able to transfer capital in between _Account Balances_.

Features:

**~ The user must be able to ~**

1. Visualise all his _Transferences_ in the given _Accounting Cycle_.
1. Visualise all his _Transferences_ of an _Account Balance_. — **Desirable Feature**
1. Create a _Transference_ of capital in between two _Account Balances_, informing: a title, a description and a date for when it happened.

<a name="Salary-Income"></a>

## Salary Income

The user must be able to create an _Transaction_ in an _Account Balance_ in order to represent some new capital that got added from the external world to the current _Accounting Cycle_.

When creating an **Income** the user must:

1. Provide a name, description and amount for it.
1. Provide to which _Account Balance_ the _Transaction_ must be added on —— **Add an check-box to mark it as a _Periodic_**.
1. Optionally, the date when it was made, or a date when it will be made (in case it's a _Periodic_).
1. The system should automatically register the date this _Income_ was inserted in the system. (**CreatedAt**)

**~ The user must be able to ~**

1. Visualize all incomes.
1. Edit a _Salary Income_.
1. Remove a _Salary Income_.
1. Copy _Salary Income_.

---

#### Use case 01 — My Hard-Earned Money

After a whole month of hard work, the user owns one or two pay checks with his rightfully hard-earned money. He needs to keep track of that.

**~ Therefore, the user must be able to ~**

1. Create a _Salary Income_ to an _Account Balance_.

---

#### Use case 02 — Vocation Bonus! \o/

After a hole year of hard work the user will recieve an extra money from his company in order to better enjoy his time out. Hooraaay! The value he'll recieve is 1/3 of his Salary (which he had already inserted in the system).

**~ Therefore, the user must be able to ~**

1. Create a _Salary Income_ where the amount is the result of an _Expression_ applied to an existing _Income_ and add some mathematical expression to it.

---

#### Use case 03 — It's Monthly My Salary

After a hole year in the same company, recieving almost the same salary, the user would like to not have to wast time adding the same information to the system over and over again every month.

**~ Therefore, the user must be able to ~**

1. Create a _Salary Incomes_ as a _Periodic Transaction_.
1. Add a _Periodic Transaction_ for only a certain amount of _Accounting Cycle_.
1. Apply the _Transaction_ to the _Account Balance_ at any time we wants in the future but still within the _Accounting Cycle_, if the _Salary Income_ is a _Periodic Transaction_.
1. Make a _Salary Income_ repeatable every _Accounting Cycle_ as _Periodic Transaction_.
1. Make a _Salary Income_ not repeatable anymore from a certain _Accounting Cycle_.
1. The repeatable _Periodic Transaction_ might occour for an unlimited or limited amount of _Accounting Cycles_.
1. When removing a _Salary Income_ that has a _Periodic Transaction_, the user must choose beteween deleting only the current _Salary Income_ or all the _Periodic Transaction_ with it.

PS².: It's up for debate if a copy functionality would be enough instead of the _Periodic Transaction_. Perhaps both funcionality should exist.

<a name="Outcome"></a>

## Outcome

The user must be able to create an _Account Transaction_ from a _Account Balance_ to the external world that represents an expense that he had during this _Accounting Cycle_.

When creating a Outcome, the user must provide the same information of the Income. (**Should be converted to only _Transaction_**)

**~ The user must be able to ~**

1. Visualize all _Outcome_ in the _Accounting Cycle_.
1. Remove an _Outcome_.
1. Edit an _Outcome_.

---

#### Use case 01 — The Taxi Bill

The user had a belly ache and needed to go to the hospital. To do that fast, he got a taxi. Now he needs to register this expense.

**~ Thefore, the user must be able to ~**

1. Create an _Outcome_ representing an expense the user had on to the _Account Balance_.

---

#### Use case 02 — The Energy Bill

The user just recieved is energy bill and the price was a bad surprise. Now, he wants to prevent this by adding it to his current mounth expenses (_Accounting Cycle_), a _Periodic Transaction_ for the next _Accounting Cycle_ energy expense.

**~ Thefore, the user must be able to ~**

1. Create an _Outcome_ as a _Periodic Transaction_, that is, not yet paid.
   1. Mark as payed the _Periodic Transaction_ _Outcome_.
1. Create an repeatable _Outcome_ — just like in _Salary Income_.

---

#### Use case 03 — The Grocery

**Story 1** — In the end of his _Accounting Cycle_, the user noticed he expend too much on other things leaving not enough money for grocery in the last week of the month. If only he could have reserved the correct amount of money, that could have been avoided.

**Story 2** — By the end of an _Accounting Cycle_, the user just noticed he expended way too much money only on his recurrent groceries. He knew he should not have brought all that junk food! If only we could track his expenses on groceries to see if it's reaching his monthly budget...

**~ Thefore, the user must be able to ~**

1. Create _Outcome_ where its amount is an _Expression_ in order to make partial payment of this _Periodic Transaction_ (**Budget??**). 

---

#### Use case 04 — I need a Medical Appointment Again

**Story 1** — In a cold day of winter, the users daughter woke up with a burning feaver; He immediatly took her to the a doctor and took note of the appointment expense in the system. She got better, but one week later, already in the next month, her medical condition went bad again, and the user had to take her back to the same medical appointment.

The user would like to copy all the expense's information from the last medical appointment since it's going to be exactly the same, only, maybe, with a different value.

**Story 2** — The user had just came back to his Psicological appointment; but he already had one last week, still in this same month, and had added this expense to the system. We would like to copy the same expense from before since they are equal.

**~ Thefore, the user must be able to ~**

1. Create a new _Outcome_ by selecting and coping another one from inside or outside the current _Accounting Cycle_.

<a name="Sporadic-Income"></a>

## Sporadic Income

The user may be able to create an _Income_ that is sporadic, taking effect in an _Account Balance_; that would represent some unexpected or not very important income that users just recieved, like some money from a splitted diner.

When creating a _Outcome_, the user must provide the same information of the _Income_.

**~ The user must be able to ~**

1. Visualize all _Sporadic Income_ in the _Accounting Cycle_ together with the _Outcomes_.
1. Remove a _Sporadic Income_.
1. Edit a _Sporadic Income_.

---

#### Use case 01 — Helping a Relative Out

**Story 1** — On a bright summer day, the user recieved a call from his aunt. She needed to lend some money to go to the doctor, she had no money at the time and asked her nephew to lend her the money. She's a woman of her word and promissed him that she would give the money back as soon as possible. The user wants to borrow the money, but he doesn't want to affect his _Predicted Free Balance_ (**Month Budget??**).

**Story 2** — On a happy sunday, the user went out for a bar with some friends. From there they decided to go somewhere else, and to make it quick the user paid the whole bill and his friend would refund him later. The user wanted to add this _Transference_ (**Expense/Transaction??**) that occoured in his _Account Balance_ without compromissing his _Predicted Free Balance_ (**Month Budget??**).

**~ Thefore, the user must be able to ~**

1. Add create a _Sporadic Income_ related with an _Outcome_. — Perhaps by throw the expressions?
1. Create multiple _Sporadic Income_ related to a single _Outcome_.

<a name="Predict-Free-Balance"></a>

## Predict Free Balance

The Final object of this project is to give the user a very good idea of how much he can expend in his month without compromising his financial wealth. For that we need to have a clear view of this number.

---

#### Use case 01 — Keep me on the track

After adding all his incomes, total amount in his accounts, and all his projected expenses for the month, like water and energy bills; the user now wantes to see how much money is free for him so he can safely expend.

**~ Thefore, the user must be able to ~**

1. Visualize, clearly and easily, the projected free amount for the current _Accounting Cycle_.
