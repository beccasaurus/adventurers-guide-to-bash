# ⚔️

Addition, Subtraction, Multiplication, Division.

![Arithmetic](Arithmetic.jpg)

---

# Bash Arithmetic

Bash supports 4 ways of performing arithmetic:
- Double Parentheses `(( expression ))`
- Dollar Parentheses `$(( expression ))`
- Let `let variable="expression"`
- Expr `expr expression`

These are all great for _different circumstances._

These all use the _same expression syntax_, however.

We'll start with the most common, most useful: [[#Double Parentheses expression|Double Parentheses]]

## Double Parentheses `(( expression ))`

Double Parentheses is generally used to:
- **Update existing variables**

*Note: Double Parentheses can also be used to:*
- *Declare new variables (Note: you must `declare -i` beforehand)*

## Dollar Parentheses `$(( expression ))`

Dollar Parentheses is generally used to:
- Perform an operation and **store the result in a variable**

*Note: Double Parentheses **can** also be used to:*
- *Declare new variables (Note: you must `declare -i` beforehand)*
- *Update existing variables*

## Let `let variable="expression"`

Let is generally used to:
- Perform an operation and **store the result in a variable**

*Note: Let **can** also be used to:*
- *Declare new variables (Note: you must `declare -i` beforehand)*
- *Update existing variables*


## Expr `expr expression`
Expr is generally not used.

*Note: Expr **can** also be used to:*
- *Update existing variables*
- Perform an operation and **store the result in a variable**
