You're already done!

Bash is provided by default with _nearly_ every version of Linux.

## Terminal

The first thing you need to determine is: _how to open a **Terminal**._

This is different in different Linux _distributions._

There are a few ways to do this:

- On Ubuntu, simply type <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>T</kbd>
- If your distribution of Linux has an application launcher, open it and type `Terminal` and see if any applications show up!
- If none of these options work, search online.

### Open Terminal

Once you have a terminal open, you should be staring at a "black box" or "white box" similar to the one shown below:

![Screenshot of a Terminal](Terminal.png)

> Note: there is a small chance that your Linux distribution's **terminal** does not use Bash, by default.
> 
> You can check by typing the following and then pressing the return key <kbd>⏎</kbd>:
> ```shell
> echo $SHELL
> ```
> 
> If this does not print out `/bin/bash` or `/???/bash`, then your terminal does not use Bash by default.
>
> First, check to see if Bash is installed by running:
> ```shell
> bash --version
> ```
> This will either print the Bash version (_as seen [[#bash --version|below]]_) or it will fail.
>
> If it fails, **consult your Linux distributions's instructions for installing Bash.**
>
> Once you have determined that Bash is on your system,
> you can either:
> - Run Bash manually without changing the default by simply typing `bash` followed by the return key <kbd>⏎</kbd>
> - Change the default shell to Bash so the terminal always runs Bash
> 
> To change the default shell to Bash:
> 1. Run `which bash` to get the "path" to Bash, e.g. `/bin/bash`, or run `cat /etc/shells` to see a full list of all installed shell paths.
> 2. Run `chsh --shell [path to bash]`, e.g. `chsh --shell /bin/bash`
> 3. Close the terminal with `exit`
> 4. Open a new terminal and run `echo $SHELL` to verify that the terminal now runs Bash by default!
> 
> ℹ️ `chsh` is short for "change shell."

##### bash --version

There will be a few times in **The Adventurer's Guide to Bash** where the _version of Bash_ is mentioned.

This might be a good time to check what version of Bash you have

Type this into the terminal prompt and then press the return key <kbd>⏎</kbd>
```shell
bash --version
```

![Bash Version](TerminalBashVersion.png)

In the example above, the Bash version is `5.0.17(1)-release`.

_You can ignore everything after `5.0`._