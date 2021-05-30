## ⚔️ Numbers

- Previous: [[Base Values]]
- Next: [[Decimal Point Values]]

Addition, Subtraction, Multiplication, Division, Exponentiation, and more!

![Arithmetic](Arithmetic.jpg)

# Bash Arithmetic

Bash supports 5 ways of performing arithmetic:
- Double Parentheses `(( expression ))`
- Dollar Parentheses `$(( expression ))`
- Declare `declare -i variable="expression"`
- Let `let variable="expression"`
- Expr `expr expression`

> These all use the same syntax for [[#Arithmetic Expressions]].

Don't feel overwhelmed! Each of these is useful _in different circumstances,_ but you could *easily* write Bash for years and only use `((` and `$((`.

First, let's look at each of these 5 ways.

Then, let's take a look at the actual [[#Arithmetic Expressions]].

# Double Parentheses

Double Parentheses is generally used to:
- **Update existing variables**

*Note: Double Parentheses can also be used to:*
- *Declare new variables (Note: you must `declare -i` beforehand)*

**Most math you perform in Bash will probably use** `(( ... ))`

#### Example

```shell
declare -i i=0
echo $i

(( i++ ))
echo $i

(( i += 5 ))
echo $i
```

If you run the above code in a terminal, you will get this output:

```
0
1
6
```

`(( ... ))` is commonly used to increment counters.

`(( ... ))` expressions can also be used for [[Conditionals]] and [[Loops]], as you'll learn later on!

> Note: `(( ... ))` expressions do not output anything to the terminal!
> To print or save the output of an arithmetic expression use `$(( ... ))`.

# Dollar Parentheses

Dollar Parentheses (_aka [Arithmetic Expansion](https://www.gnu.org/software/bash/manual/html_node/Arithmetic-Expansion.html)_) is generally used to:
- **Perform an operation and get the result**


The main difference between `((...))` and `$((...))` is that `$((...))` **outputs the result of the expression:**

```shell
declare -i x=10

result=$(( x + 10 ))

echo $result
```

If you run the above code in a terminal, you get `20` as a `result`.

You could also `echo` the result directly without using a variable:

```shell
declare -i x=10

echo $(( x + 10 ))
```

Arithmetic Expansion (`$(( ... ))`) also works within quoted text:

```shell
echo "The result is: $(( x + 10 ))"
```

**As a general rule:**
- Use `$(( ))` to capture or output the result of an expression.
- Use `(( ))` to modify values _without capturing the result._

> *Note: variable values can also be modified using* `$(( ... ))`
>
> _For example: incrementing or decrementing a variable:_
>
> ```shell
> declare -i x=10
> 
> result=$(( x++ ))
> 
> echo $result
> echo $x
> ```
> 
> *Running the above in the terminal will output:*
> ```
> 10
> 11
> ```
> 
> _If you want to increment a variable AND get the new value, use `++x` instead (aka "pre-increment")_

# Declare

Declare is generally used to:
- **Declare new variables**

As seen in [[Numbers#Declaring With an Expression]], `declare -i` can accept an expression. The result will be used as the initial value of the variable:

```shell
declare -i goblin_strength=10
declare -i dragon_strength="goblin_strength * 5"
echo $goblin_strength
echo $dragon_strength
```

Running the above code will output:

```
10
50
```

This is a useful way to assign the initial value of an integer.

# Let

Let is generally used to:
- **Perform an operation and store the result in a variable**

Many people use `let` _in place of_ `declare -i`:

```shell
# ✗ DON'T DO THIS
let "goblin_strength = 10"
let "dragon_strength = goblin_strength * 5"
```

This code may _look appealing_ but it is _incorrect_ **unless** used _after_ configuring each variable using `declare -i`

```shell
# ✓ DO THIS
declare -i goblin_strength dragon_strength # <---
let "goblin_strength = 10"
let "dragon_strength = goblin_strength * 5"
```

This may seem a bit redundant, but it will save you in the future!

> Reminder for **Why** this is the correct way:
> [[Numbers#Declaring Integer Variables]]

Note: as opposed to `declare -i`, using `let` **_does_** allow you to put **spaces** between the variable name, the `=`, and the value:

```shell
declare -i x=5 # <-- no spaces before/after =
let "y = 10"   # <-- spaces allowed before/after =
               #     but quotes are *required*
```

`let` is essentially "syntax sugar" for `(( ))`. These are equivalent:

```shell
let "x = 10" # These two statements are
(( x = 10 )) # equivalent.
```

The main difference is that `let` **_requires_** using quoted text (`"` or `'`).

Also, some people simply prefer the syntax of: `let "x = 10"`.

# Expr
Expr is generally not used. **Don't use it.**





# Arithmetic Expressions

Bash supports [various arithmetic operations](https://www.gnu.org/software/bash/manual/html_node/Shell-Arithmetic.html#Shell-Arithmetic):
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