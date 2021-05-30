Variables in Bash are declared in the following way:

```shell
[declare] [options] variable_name=[variable value]
```

The `declare` keyword (_and its [options]_) are optional _in some cases._

The following **text variable** examples are equivalent:

```shell
# Long-version:
declare monster_name="Dragon"

# Short-hand:
monster_name="Dragon"
```

#### No Spaces

Note that there are _**no spaces**_ on either side of the `=` sign.

```shell
# UNSUPPORTED
monster_name = "Dragon"
monster_name= "Dragon"
monster_name ="Dragon"

# SUPPORTED
monster_name="Dragon"
```
