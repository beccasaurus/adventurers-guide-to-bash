## ⚔️

- Previous: [[What is a Shell?]]
- Next: [[What is Bash?]]

---

In the [[What is a Shell?|previous section]] you learned about "Shells" and "Command-line Interfaces" (CLIs) which execute text "commands".

So what is a "**Shell Scripting**"?

> _"A shell script is a computer program designed to be run by [a] shell, a command-line interpreter."_ [^1]

Simply put, a "**shell script**"  is a text file containing shell commands.

"**Shell scripting**" the the act ( _or the art_ ) of creating these files.

## Plain Text Files

Have you ever created a text file before?

I don't mean using a program like Microsoft Word, just _plain text._ [^2]

If you're not a programmer, the answer is likely no.

Programmers write code in "plain text files."

Depending on the programming language, these files may be given a different file extension:

- `.java` ( *Java* )
- `.py` ( *Python* )
- `.rb` ( *Ruby* )
- `.js` ( *JavaScript* )

Although the file _extensions_ may be different, these all share one thing in common: they are nothing more than simple plain text files.

## Shell Script Files

Shell scripts are plain text files.

The file extension depends on the shell which runs them:

- `.bat` ( *Run via the Microsoft  `cmd.exe` shell* ) [^3]
- `.ps1` ( *Run via the Microsoft `PowerShell` shell* ) [^4]
- `.sh` ( *Run via Unix shells, e.g. `Bash`* ) [^5]

## Unix Shell scripts `.sh`

Unix shell scripts are not run by _one particular program._

Instead, the script itself specifies _which_ shell to use when running the file.

Here are the file contents of a typical example of a Bash shell script: [^6]

```shell
#! /bin/bash
echo Hello
```

Here are the file contents of a typical example of a KornShell [^7] shell script:

```shell
#! /bin/ksh
echo Hello
```

Here are the file contents of a typical example of a Almquist [^8] shell script:

```shell
#! /bin/ash
echo Hello
```

You have probably noticed the difference by now.

Unix shell scripts are plain text files which start with a special line called the Hashbang [^9] ( _hash mark `#` followed by an exclamation mark `!`, aka "bang"_ )

The Hashbang (`#!`) is followed by the file path to a program.

When the shell script is run, the specified program runs the script.

So, what is the difference between these different shells?

Let's learn more in the next section: [[What is Bash?]]

[^1]: https://en.wikipedia.org/wiki/Shell_script
[^2]: https://en.wikipedia.org/wiki/Plain_text
[^3]: https://en.wikipedia.org/wiki/Batch_file
[^4]: https://en.wikipedia.org/wiki/PowerShell
[^5]: https://en.wikipedia.org/wiki/Unix_shell
[^6]: The use of `#! /bin/bash` is actually considered an "anti-pattern" and we will not use it in this book. It is, however, the most common "hashbang" which is used Bash shell scripts.
[^7]: https://en.wikipedia.org/wiki/KornShell
[^8]: https://en.wikipedia.org/wiki/Almquist_shell
[^9]: The "hashbang" is also commonly known as the "shebang." This book exclusively uses the term "hashbang." Wikipedia: https://en.wikipedia.org/wiki/Shebang_(Unix)