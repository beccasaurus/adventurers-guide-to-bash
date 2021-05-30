BSD often uses the classic Bourne Shell (`/bin/sh`) [^1] or `tsch` [^2] by default.

To install Bash on FreeBSD, run the following in a terminal [^3]

```shell
pkg update
pkg install bash
```

Once installation is complete, try this command to ensure Bash is installed:

```shell
bash --version
```

Now, you can launch an interactive Bash shell by simply running `bash` in the terminal.

If you would like to switch your **default** terminal shell to always use Bash:
```shell
chsh -s `which bash` $USER
```


[^1]: https://en.wikipedia.org/wiki/Bourne_shell
[^2]: https://en.wikipedia.org/wiki/Tcsh
[^3]: You're running BSD. I'm assuming you know how to open a terminal. If not, I advise searching the internet or follow instructions similar to [[Linux#Terminal]]