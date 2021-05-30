## ⚔️

- Previous: [[Lesson Plan]]
- Next: [[Numbers]]

---

Like most programming languages[^1], Bash provides **variables**.

# Variables, what are they good for?

Variables allow you to associate a descriptive name with a value:

```shell
monster="Goblin"
type="Humanoid"
weapon="Scimitar"
```

Variables allow you to use a variable throughout your program:

```shell
echo "The $monster is a $type creature that carries a $weapon"
# => The Goblin is a Humanoid creature that carries a Scimitar
```

# Types of Variables

Bash supports 3 different types of variables:

- [[Numbers]]
- [[Text]]
- [[Lists]]

```shell
monster="Dragon"              # Text
enemies=("Goblins" "Dwarves") # List
declare -i strength=10        # Number

echo "$name has a strength of $strength"
# => Dragon has 10 strength

echo "$name enemies: ${enemies[*]}"
# => Dragon enemies: Goblins Dwarves
```

You will learn *each variable type* in depth.

**But first, let's overview the basics of Bash variables!**




![[Declaring Variables]]

[^1]: Note: [Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) is specifically a [command language](https://en.wikipedia.org/wiki/Command_language), not a general-purpose Programming Language.