## ⚔️

- Previous: [[Lesson Plan]]
- Next: [[Numbers]]

# Bash Variables

Like most programming languages[^1], Bash provides **variables**.

Variables are used to store different types of values in your program.

Bash supports 3 different types of variables:

- [[Numbers]]
- [[Text]]
- [[Lists]]

#### Example of Using Variables in Bash:

```shell
monster_name="Dragon"                 # Text
monster_strength=10                   # Number
monster_enemies=("Goblins" "Dwarves") # List

echo "$monster_name has $monster_strength strength"
# => Dragon has 10 strength

echo "$monster_name enemies: ${monster_enemies[*]}"
# => Dragon enemies: Goblins Dwarves
```

You will learn *each variable type* in depth.

**But first, let's overview the basics of Bash variables!**

---

# Declaring Variables

In Bash, the simplest way to declare a variable is by using this syntax:

`[variable name]=[variable value]`

```shell
monster_strength=10
```

The example above:
- Creates a new variable with the name `monster_strength`
- Assigns it the value `10`

> Note: there are _**no spaces**_ between the variable name, `=`, and value.

## declare

The `[variable name]=[variable value]` syntax is Bash shorthand for:  

```shell
declare [variable name]=[variable value]`
```

# Using Variables

Once a variable has been declared, its value can be **referenced** using the `$` sign, followed by the name of the variable:

```shell
monster_strength=10
echo $monster_strength # <--- notice the $
```

Try pasting the above code into your terminal. It should print `10`.

#### Variables in Text

Variables may also be used in text blocks wrapped by `"` quotes:

```shell
monster_name="Dragon"
monster_strength=10

echo "$monster_name has $monster_strength strength"
# => Dragon has 10 strength
```

Try the above code in your terminal.

It should print `Dragon has 10 strength`.

_**Text variables will be covered in depth later in the lesson**._

# Variable Names

Variable names must:
- Start with a letter `A - Z` (*uppercase*) or `a - z` (*lowercase*)
- May only contain letters, numbers, and underscores.

## What should I name my variable?

When writing programs, you should choose variable names that will help you remember what the program does when you revisit the code later.

There is a common misconception that:
- Programmers like to use short variable names (_e.g. to save memory_)
- Programmers write lots of "code comments" to document their code

These are false. Instead, programmers _name things_ well so that _documentation is not necessary._

```shell
# PLEASE DO NOT DO THIS:

m="Dragon" # <--- No!
str=10     # <--- No!

echo "$m has $str strength"
```

There is no reason to shorten a variable like `monster_name` to `m`.

This may save you a few keystrokes **now** _but you'll regret it **later**._

### Should I name variables `fooBar` or `foo_bar` or `FOO_BAR`?

This is actually completely up to you!

The most important thing is _**consistency**._

If you choose to name your variables `soTheyLookLikeThis` then you should _not_ also name your variables `so_they_look_like_this`!

_Note: once you're further along in your learning, you can read my [[Variable Names|recommendation for variable naming]] in the [[Style Guide]]._

# Printing Variables

In later sections, you will learn the Bash `declare` builtin.

If you ever want to print the full Bash representation of a variable, use:

`declare -p [variable name]`

( _The `-p` stands for `print`_ )

```shell
monster_strength=10
declare -p monster_strength
```

If you run the above code in a terminal, the output will be:

```
declare -- monster_strength="10"
```

**Why in the world would this be useful?**


# Variable Types

Bash supports 3 different types of variables:

- [[Numbers]]
- [[Text]]
- [[Lists]]

Next, you will walk through each of these types and learn how to use them!

We'll be starting with [[Numbers]]!

[^1]: Note: [Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) is specifically a [command language](https://en.wikipedia.org/wiki/Command_language), not a general-purpose Programming Language.
