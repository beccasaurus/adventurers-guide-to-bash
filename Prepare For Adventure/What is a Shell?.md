## ⚔️

- Previous: [[Installing Bash]]
- Next: [[What is a Shell Scripting?]]

---

> _"a **shell** is a computer program which exposes an operating systems's services to a [program]"_ [^1]

There are two types of computer **shells**:
- "Graphical shells" ( _not relevent for learning Bash_ )
- "Command-line shells" ( _very relevant for Bash!_ )

Bash is  a **command-line shell**, so let's just focus on those!

## Command-line interfaces

What is a command-line interface? Let's look at an example.

Operating Systems (_e.g. Windows, macOS, Linux_) have files and folders, right?

Most operating systems provide a graphical-user interface (GUI) for browsing, creating, and deleting files.

But there is an alternate way to manage files: **command-line interfaces**.

> _"A **command-line interface** (**CLI**) processes commands to a computer program in the form of lines of text."_ [^2]

Using a GUI, one might right-click > "New Folder" to create a folder.

But using a CLI, one might type the `mkdir` *command* (_short for `m`a`k`e `dir`ectory_) into a computer terminal (_we'll get to [[What is a Terminal?|terminals]] later_):

```shell
mkdir MyFolder
```

> `mkdir` is an example of a "command", hence the term "*command*-line interface".

Using a GUI, one might double-click a folder to enter it and browse its contents.

But using a CLI, one might use the `cd` (_`c`hange `d`irectory_) command to enter a directory and then the `ls` (`l`i`s`t) command to list its contents:

```shell
cd MyFolder
ls
```

The command-line interface is made possible by a command-line shell.

[Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) is an example of a [command-line shell](https://en.wikipedia.org/wiki/Shell_(computing)#Command-line_shells).

## Why CLI?

Using a command-line interface might seem inefficient.

Why type these commands, e.g. `mkdir`, rather than just using a GUI?

Well, it's easy to create one folder using the GUI. But what about 100 folders?

```shell
mkdir photos-{1..100}
```

What if you want to resize a photo? There are GUI programs which can do this for you. But what if you need to resize 100 photos?

```shell
for photo in MyPhotos/
do
	convert $photo -resize 50% $photo
done
```

Command-line interfaces can make it much easier to:
- Perform bulk operations, *e.g. resizing 100 photos*
- Perform scheduled operations, *e.g. a task to run once a day*

It is especially powerful when you combine multiple commands together into [[What is a Shell Scripting?|scripts]], which is what we'll look at next.

[^1]: https://en.wikipedia.org/wiki/Shell_(computing)
[^2]: https://en.wikipedia.org/wiki/Command-line_interface