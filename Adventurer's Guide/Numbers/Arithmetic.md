# ⚔️

Addition, Subtraction, Multiplication, Division, Modulo, Exponentiation.

![Arithmetic](Arithmetic.jpg)

---

# Bash Arithmetic

Bash supports 5 ways of performing arithmetic:
- Double Parentheses `(( expression ))`
- Dollar Parentheses `$(( expression ))`
- Declare `declare -i variable="expression"`
- Let `let variable="expression"`
- Expr `expr expression`

These are all great for _different circumstances._

These all use the _same expression syntax_, however.

First, let's take a look at the *different ways of performing arithmetic.*

Then, let's take a look at [[#Bash Arithmetic Expressions]].

# Double Parentheses `(( expression ))`

Double Parentheses is generally used to:
- **Update existing variables**

*Note: Double Parentheses can also be used to:*
- *Declare new variables (Note: you must `declare -i` beforehand)*

Most math you perform in Bash will probably use `(( ... ))`

Example:

```shell
declare -i i=0
echo $i

(( i++ ))
echo $i

(( i++ ))
echo $i
```

If you run the above code in a terminal, you will get this output:

```
0
1
2
```

`(( ... ))` is commonly used to increment counters.

But you can also perform:
- **Addition** `+`
- **Subtraction** `-`
- **Multiplication** `**`
- **Division** `/`
- **Modulo** `%`
- **Exponentiation** `**`

`(( ... ))` expressions can also be used for [[Conditionals]] and [[Loops]], as you'll learn later on!

> Note: `(( ... ))` expressions do not output anything to the terminal!
> To print or save the output of an expression use `$(( ... ))`.

# Dollar Parentheses `$(( expression ))`

Dollar Parentheses (_aka [Arithmetic Expansion](https://www.gnu.org/software/bash/manual/html_node/Arithmetic-Expansion.html)_) is generally used to:
- Perform an operation and **store the result in a variable**

*Note: Double Parentheses **can** also be used to:*
- *Declare new variables (Note: you must `declare -i` beforehand)*
- *Update existing variables*

# Declare `declare -i variable="expression"`

Declare is generally used to:
- *Declare new variables

*Note: Declare **can** also be used to:*
- *Update existing variables*
- Perform an operation and **store the result in a variable**

# Let `let variable="expression"`

Let is generally used to:
- Perform an operation and **store the result in a variable**

*Note: Let **can** also be used to:*
- *Declare new variables (Note: you must `declare -i` beforehand)*
- *Update existing variables*


# Expr `expr expression`
Expr is generally not used.

*Note: Expr **can** also be used to:*
- *Update existing variables*
- Perform an operation and **store the result in a variable**


# Bash Arithmetic Expressions