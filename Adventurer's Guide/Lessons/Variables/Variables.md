# ⚔️

Welcome to the first section! Let's learn about Bash variables.

![Adventurer's Guide](AdventurersGuide.jpg)

---

Like most programming languages[^1], Bash provides **variables**.

Variables are used to store different types of values in your program.

```shell
greeting="Hello"
recipient="World"

echo "$greeting, $recipient!"
# => Hello, World!
```

---

## Defining Variables

In Bash, the simplest way to define a variable is by using the  
`[variable name]=[variable value]` syntax (_as seen above_).

In this example, a variable named `my_variable` is defined and set to `42`:

```shell
my_variable=42
```

Variables are useful so your program can re-use a value in many places.

### Using Variables

Once a variable has been defined, its value can be referenced using the `$` sign followed by the name of the variable:

```shell
my_variable=42
echo $my_variable
```

Try pasting the above code into your terminal. It should print `42`

###### Variables in Text

Variables may be used in text blocks wrapped by `"` quotes as well:

```shell
greeting="Hello"
recipient="World"

echo "$greeting, $recipient!"
```

Try the above code in your terminal. It should print `Hello, World!`.

_Text variables will be covered in depth later in the lesson._

### Variable Names

Variable names must:
- Start with a letter `A - Z` (*uppercase*) or `a - z` (*lowercase*)
- May only contain letters, numbers, and underscores.

###### What should I name my variable?

When writing programs, you should choose variable names that will help you remember what the program does when you revisit the code later.

There is a common misconception that:
- Programmers like to use short variable names (_e.g. to save memory_)
- Programmers write lots of "code comments" to document their code

These are false. Instead, programmers _name things_ well so that _documentation is not necessary._

```shell
# DO NOT DO THIS:
g="Hello"
r="World"
echo "$g, $r!"

# INSTEAD, USE LONGER, MORE
# DESCRIPTIVE VARIABLE NAMES
```

###### Should I name variables `fooBar` or `foo_bar` or `FOO_BAR`?

This is actually completely up to you.

The most important thing is _consistency._

If you choose to name your variables `soTheyLookLikeThis` then you should _not_ also name your variables `so_they_look_like_this`.

_Note: once you're further along in your learning, you can read my [[Variable Names|recommendation for variable naming]] in the [[Style Guide]]._

### Variable Types

Bash supports 3 different types of variables:

- [[Numbers]]
- [[Text]]
- [[Lists]]

Next, you will walk through each of these types and learn how to use them!


[^1]: Note: [Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) is specifically a [command language](https://en.wikipedia.org/wiki/Command_language), not a general-purpose Programming Language.