# ⚔️

Addition, Subtraction, Multiplication, Division, Exponentiation, and more!

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

But you can also perform [various arithmetic operations](https://www.gnu.org/software/bash/manual/html_node/Shell-Arithmetic.html#Shell-Arithmetic):
- **Addition** `+`
- **Subtraction** `-`
- **Multiplication** `**`
- **Division** `/`
- **Remainder** `%`
- **Exponentiation** `**`
- **Bitwise Shifts** `<<` `>>`
- **Pre-increment/decrement** `++x` `--x`
- **Post-increment/decrement** `x++` `x--`
- [and more](https://www.gnu.org/software/bash/manual/html_node/Shell-Arithmetic.html#Shell-Arithmetic)

`(( ... ))` expressions can also be used for [[Conditionals]] and [[Loops]], as you'll learn later on!

> Note: `(( ... ))` expressions do not output anything to the terminal!
> To print or save the output of an expression use `$(( ... ))`.

# Dollar Parentheses `$(( expression ))`

Dollar Parentheses (_aka [Arithmetic Expansion](https://www.gnu.org/software/bash/manual/html_node/Arithmetic-Expansion.html)_) is generally used to:
- Perform an operation and **store the result in a variable**

*Note: Double Parentheses **can** also be used to:*
- *Declare new variables (Note: you must `declare -i` beforehand)*
- *Update existing variables*

The main difference between `((...))` and `$((...))` is that `$((...))` **outputs the result of the expression:**

```shell
declare -i x=10

# (( )) increments the value without outputing to the terminal
(( x++ ))
echo "x is $x"

# $(( )) outputs a value which can be used, e.g. by providing to echo
echo "Now x is $(( ++x ))"
```

If you run the above code in a terminal, you will get this output:

```
x is 11
Now x is 12
```

Use `$(( ))` to capture the result.

Use `(( ))` to modify values _without capturing the result._

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