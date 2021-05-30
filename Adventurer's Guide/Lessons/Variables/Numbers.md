## ⚔️

- Previous: [[Variables]]
- Next: [[Base Values]]

**Numbers, numbers, numbers.**

![D6 Dice](Numbers.jpg)


# Bash Numbers

In this section, you will learn how to work with numbers in Bash.

- [[Numbers#Declaring Integer Variables|Declaring Integer Values]]
- [[Base Values|Using Different Bases]]
- [[Arithmetic]]
- [[Decimal Point Values]]

## Supported Numbers

- Supported: Decimal Integers (_no decimal point values_)
	- e.g. `1`, `2`, `3`, `4`, `5`, `100`, `1000`, etc
	- _All the way up to _`9,223,372,036,854,775,808` 
	- _Note: Bash does not support using the `,` in numbers_
- Supported: Octal numbers
- Supported: Hexadecimal numbers
- Supported: Any other base between 2 and 64

## Unsupported

Bash does **not** natively support numbers with **decimal points**:
- Unsupported: `3.14`, `1.1`, `2.1`, `4.20`, etc

ℹ️ There are ways to work with [[Decimal Point Values]] using Bash.

This will be covered later in the lesson.

# Declaring Integer Variables

The *simplest* way to declare variables with numeric values in Bash is by using the `[variable name]=[variable value]` syntax, as shown in [[Variables|the previous section]]:

```shell
dragon_strength=10
goblin_strength=5
```

This is **not** how we will be declaring integers, however.

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

( _The `-i` stands for `integer`_ )

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

Once a variable has been declared via `declare -i`, it can somewhat safely[^1] be set in other ways, e.g. using the `[variable name]=[variable value]` syntax.

> ℹ️ Setting a `declare -i` variable to a non-number will **not** always result in an error. When an integer is set to `A - Z` text _without spaces_, it will _**set the value to 0**_ instead of raising an explicit error:
> ```shell
> declare -i strength=10
> echo $strength
> strength=SomeTextHere
> echo $strength
> ```
> 
> The above example will output `10` and then `0`.
> 
> You can use [[Arithmetic#Let|let]] or [[Arithmetic#Double Parentheses|(( ... ))]] to force an error!

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

This is often useful when you _don't know the value_ of a variable (_the program will set the value later_), but you want to be **_certain_** that the variable is treated as an integer.

> ℹ️ `declare -i` can declare multiple integer variables at once:
> - `declare -i foo`
> - `declare -i foo=20 bar`
> - `declare -i foo=20 bar=40 baz=60`

## Declaring With an Expression
When declaring a variable with `declare -i`, an expression may be provided to set the initial value of the variable:

```shell
declare -i a="1 + 4" b="a + 1" c="b * 2"
echo $a
echo $b
echo $c
```

If you run the example above in the terminal, you will get the output:

```
5
6
12
```

This will be covered more in the upcoming [[Arithmetic]] section.

> ⚠️ Warning: `declare -i x="Hello"` does **not fail**.
> 
> It is best practice to use `(( ... ))` or `let` instead:
> ```shell
> declare -i x
> 
> (( x = Hello )) # <-- this fails! ✓
> let x=Hello     # <-- this fails! ✓
> let "x = Hello" # <-- this fails! ✓
> ```

## Modifying Integer Variables

Once a variable has been **declared as an integer** using `declare -i`, there are 3 common ways to set or modify the variable's value:

1. Simple: `[variable name]=[variable value]` (_Not recommended_)
3. Double Parentheses: `(( [variable name] = arithmetic expression ))`
2. Let: `let [variable name]="[arithmetic expression]"`

These will each be reviewed in the upcoming [[Arithmetic]] section.

**But let's take a quick sneak-peek at what they look like!**

### Simple x=[value]

This is the same method seen above, it is the simplest method:

```shell
declare -i x=5
x=10
x=20
```

*This method only supports "static values", e.g. `10` or `20`, and does not perform arithmetic expressions.*

> **This is not recommended.**  
> **Please use `(( ... ))` or `let`.**

> ℹ️ Note: if you try to set `x="Hello"`, this will **not** cause an error.
> Both `(( x = Hello ))` and `let "x = Hello"` **do** fail (_which is good_)

### Double Parentheses (( expression ))

Double parentheses `(( ... ))` perform [[Arithmetic]] in Bash.

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

### Let x="expression"

`let` allows you to easily set the value of a variable to the result of an [[Arithmetic]] expression.

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



# Bash Numbers

In this section, you learned how to **declare** integer variables in Bash.

Next up, you will learn more about using numbers in Bash!

- [[Base Values|Using Different Bases]] _(Optional)_
- [[Arithmetic]]
- [[Decimal Point Values]]

After numbers, you'll move on to:
- [[Text]] variables
- [[Lists]] variables

[^1]: Even if a variable is declared with `declare -i`, trying `varname=Hello` will set the variable to `0` _but_ it will not _fail_ (_it returns a 0 exit code_). If you want to ensure that your script fails when an invalid value is given to an integer value, use `let` or `(( ... ))` to assign variable values. This is the safest and recommended way.