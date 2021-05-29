# ⚔️

Numbers, numbers, numbers.

![D6 Dice](Numbers.jpg)

---

# Bash Numbers

In this section, you will learn how to work with numbers in Bash.

- [[Numbers#Declaring Integer Variables|Declaring Integer Values]]
- [[Arithmetic]]
- [[Decimal Values]]

---

# Integers and Decimals

Bash does not natively support numbers with decimal points:

- Supported: `1`, `2`, `3`, `4`, `5`, `100`, `1000`, etc
	- _All the way up to _`9,223,372,036,854,775,808` 
	- _Note: Bash does not support using the `,` in numbers_
- Unsupported: `3.14`, `1.1`, `2.1`, `4.20`, etc

This section focuses on working with _**integer** values._

> ℹ️ There are ways to work with [[Decimal Values]] using Bash.
> This will be covered later in the lesson.

# Declaring Integer Variables

The *simplest* way to declare variables with numeric values in Bash is by using the `[variable name]=[variable value]` syntax, as shown in [[Variables|the previous section]]:

```shell
dragon_strength=10
goblin_strength=5
```

This is **not** how we will declare integers, however.

**Here is why:**

```shell
dragon_strength=10
echo $dragon_strength

dragon_strength="Changed it to text"
echo $dragon_strength
```

Try the above in the terminal and you will get this output:

```
10
Changed it to text
```

**Why is this a problem?**

Your program may perform arithmetic, e.g. it may multiply `10 * dragon_strength`.

What will happen if the program tries to multiply `10 * "Changed it to text"`? Kaboom!

Instead, to **ensure** your variables are integer values, we will use `declare`.

# declare -i varname

The correct way to work with integers in Bash is to use `declare -i`.

I have updated the previous example to demonstrate how it works:

```shell
declare -i dragon_strength=10
echo $dragon_strength

dragon_strength="Changed it to text"
echo $dragon_strength
```

Try the above in the terminal and you will get this output:

```
10
bash: Changed it to text: syntax error in expression (error token is "it to text"
10
```

It breaks! _How wonderful!_ That's great, because it's not a number!

Using `declare -i [variable name]` declares a variable **_as an integer_** and it will always be an integer, regardless of what value it's set to.

> ℹ️ Setting a `declare -i` variable to a non-number will **not** always result in an error. When an integer is set to a single word _without spaces_, it will _**set the value to 0**_ instead of raising an error.

## Declaring Without a Value

You can also `declare -i dragon_strength` _without_ providing a value.

This declares that the `dragon_strength` variable is, _and will always be_, an integer.

Then, later code can modify the value using simple `[variable name]=[variable value]` syntax:

```shell
declare -i x y # <--- declares 2 integer variables, x and y
echo "x is $x and y is $y"

x=10 # <--- set the values of the declared integer variables
y=20
echo "x is $x and y is $y"
```

Running the above code in a terminal will output:

```
x is  and y is  
x is 10 and y is 20
```

This is often useful when you _don't know the value_ of a variable (_the program will set the value later_), but you want to make _sure_ that the variable is treated as an integer.

> ℹ️ `declare -i` can declare multiple integer variables at once:
> - `declare -i foo`
> - `declare -i foo=20 bar`
> - `declare -i foo=20 bar=40 baz=60`

## Declaring With an Expression
When declaring a variable with `declare -i`, an expression may be provided to set the initial value of the variable:

```shell
declare -i a=1 b="a+1" c="b+1"
echo $a
echo $b
echo $c
```

If you run the example above in the terminal, you will get the output:

```
1
2
3
```

This will be covered more in the upcoming [[Arithmetic]] section.

## Modifying Integer Variables

Once a variable has been **declared as an integer** using `declare -i`, there are 3 ways to set or modify the variable's value:

1. Simple: `[variable name]=[variable value]`
3. Double Parentheses: `(( [variable name] = arithmetic expression ))`
2. Let: `let [variable name]="[arithmetic expression]"`

### Simple x=[value]

This is the same method seen above, it is the simplest method:

```shell
declare -i x
x=10
x=20
```

### Double Parentheses (( expression ))

Double parentheses `(( ... ))` perform [[Arithmetic]] in Bash.

[[Arithmetic]] will be covered next, but here is a brief example:

```shell
declare -i x=10
echo $x

(( x = x + 5 ))
echo $x
```

If you run the example above in the terminal, you will get the output:

```shell
10
15
```

_We will look at this more in depth momentarily._

### Let x="expression"

`let` allows you to easily set the value of a variable to the result of an [[Arithmetic]] expression.

[[Arithmetic]] will be covered next, but here is a brief example:

```shell
declare -i x=10
echo $x

let x="x + 5"
echo $x
```

If you run the example above in the terminal, you will get the output:

```shell
10
15
```

_We will look at this more in depth momentarily._

# Bash Numbers

In this section, you learned how to **declare** integer variables in Bash.

The next sections are **references** for performing [[Arithmetic]] and working with [[Decimal Values]] in Bash:

- [[Arithmetic]]
- [[Decimal Values]]

These sections are **not** part of the written lesson plan.

Once you are done, be sure to return back to [[Variables]] for the next sections on [[Text]] and [[Lists]] variables.
