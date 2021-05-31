## ⚔️

- Previous: [[Installing Bash]]
- Next: [[What is a Shell Scripting?]]

---

> _"a **shell** is a computer program which exposes an operating systems's services to a [program]"_ [^1]

Operating Systems (_e.g. Windows, macOS, etc_) have files and folders.

Most operating systems provide a graphical-user interface (GUI) for browsing, creating, and deleting files.

But there is an alternate way to edit files: **command-line interfaces**.

> _"A **command-line interface** (**CLI**) processes commands to a computer program in the form of lines of text."_ [^2]

Using a GUI, one might right-click > "New Folder" to create a folder.

But using a CLI, one might type the `mkdir` command (_short for `m`a`k`e `dir`ectory_):

```sh
mkdir MyFolder
```

Using a GUI, one might double-click a folder to enter it and browse its contents.

But using a CLI, one might use the `cd` (_`c`hange `d`irectory_) and `ls` (`l`i`s`t) commands to enter a directory and list its contents:

```shell
cd MyFolder
ls
```

Both the GUI and CLI programs (_e.g. which allow you to edit files_) are called **shells**.

[Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) is an example of a [command-line shell](https://en.wikipedia.org/wiki/Shell_(computing)#Command-line_shells).

> _"A [command-line interface](https://en.wikipedia.org/wiki/Command-line_interface "Command-line interface") (CLI) is an operating system **shell** that uses [alphanumeric](https://en.wikipedia.org/wiki/Alphanumeric "Alphanumeric") characters typed on a keyboard to provide instructions and data to the operating system, interactively."_ [^3]

[^1]: https://en.wikipedia.org/wiki/Shell_(computing)
[^2]: https://en.wikipedia.org/wiki/Command-line_interface
[^3]: https://en.wikipedia.org/wiki/Shell_(computing)#Command-line_shells