To write and develop Bash applications on an Android phone or tablet, you will need two or three things:

1. (_Optional_) **Keyboard** which works well for code ( _rather than texting_ )
1. **Text Editor** to write and edit Bash scripts ( _plain-text files_ )
1. **Bash** ( _e.g. a Linux environment running on Android with Bash_ )

As of 2021, there is really only one good option for running **Bash** on Android: [[#Termux]].

There are _multiple_ text editors available, but I recommend the free, powerful [[#Acode]] **Text Editor**.

The following instructions will get you up-and-running with Bash on your Android device!

- [[#Hacker's Keyboard]]
- [[#Acode]] Text Editor (_with Bash support!_)
- [[#Termux]] Linux Environment (_with Bash!_)

# Hacker's Keyboard
![Hacker's Keyboard Logo](HackersKeyboardLogo.png)

_(Optional)_

The built in Google Keyboard supports auto-correct which works great (_sometimes_) for writing text messages and emails.

The Gboard auto-complete is _not so great_ when writing code.

If you are using a _physical keyboard_ with your Android device, then this is less important.

If you're using a touchscreen, I recommend installing: [Hacker's Keyboard](https://play.google.com/store/apps/details?id=org.pocketworkstation.pckeyboard&hl=en_US&gl=US) from the [Google Play Store](https://play.google.com/store/apps/details?id=org.pocketworkstation.pckeyboard&hl=en_US&gl=US).

When writing code, you'll want easy access to characters such as `$`, `{`, `[`, `>`, etc. This keyboard will help!

1. **Install** Hacker's Keyboard
2. **Open** Hacker's Keyboard
3. **Enable keyboard**
4. Set **Keyboard mode, portrait** and **Keyboard mode, landscape** to use the option:
	- `5-row compact layout (US QWERTY only!)`
	- _for non-US QWERTY users, choose:_ `Full 5-row layout`
5. Try it out!

> **Instructions** (_shown when opening the application_)
> ![Hacker's Keyboard Instructions](HackersKeyboardInstructions.jpg)

> Click **Enable keyboard** and say `OK` to all of the options.
> Then use the toggle switch to enable the keyboard.
> ![Hacker's Keyboard Enable](HackersKeyboardEnable.jpg)

> Change the **Keyboard mode** in **Settings**.
> The default keyboard does not give easy access to `{` and other characters which you will want regularly in Bash.
> ![Hacker's Keyboard Change Mode](HackersKeyboardMode.jpg)

> To switch between the default **Gboard** and the **Hacker's Keyboard**, open the **Gboard** (_e.g. by clicking the `Test` text on the settings page_), click the little keyboard icon in the _very bottom right_ of the **Gboard**.
> 
> This will give you an option to switch to the **Hacker's Keyboard**.
>
> Use the same method to switch back to the **Gboard** as desired.
> ![Hacker's Keyboard Choose](HackersKeyboardChoose.jpg)

# Acode

![Acode Logo](AcodeLogo.png)

There are multiple Text Editors on Android.

*If you already use a Text Editor which supports syntax highlighting code files on your Android device, try using your existing editor!*

But I _highly_ recommend using the free, powerful code editor: [Acode](https://acode.foxdebug.com/)

Acode has _built-in support_ for editing Bash files, which is _super helpful._

1. [Install Acode](https://play.google.com/store/apps/details?id=com.foxdebug.acodefree&hl=en_US&gl=US) from the [Google Play Store](https://play.google.com/store/apps/details?id=com.foxdebug.acodefree&hl=en_US&gl=US)
2. Open Acode
3. Allow Acode to access your device files
4. Create a new folder to put your Bash files
5. Create a new Bash script: `hello.sh`
6. Add Bash code to the file: `echo "hello world"`
7. Save the file

> Allow **Acode** access to your files upon opening the application:
> ![Acode Allow Access](AcodeAllow.jpg)

> Tap the 📁 to enter the `Internal storage` folder.
> ![Acode Internal Storage Folder](AcodeInternalStorage.jpg)

> Tap the ➕ in the upper right and choose `New Folder` and name it whatever you like, e.g. `Adventure`.
> 
> This is where you can store all of your files while reading through **The Adventurer's Guide to Bash**.
>
> _Recommendation: While adventuring, you will likely want to organize your files into additional subfolders._
> ![Acode New Folder](AcodeNewFolder.jpg)


> Tap the 📁 to enter the `Adventure` folder.
> ![Acode Adventure Folder](AcodeAdventureFolder.jpg)

> Tap the ➕ in the upper right and choose `New File` and name it `hello.sh`
> ![Acode New File](AcodeNewFile.jpg)

> Tap the back arrow (_or swipe right_) to go back to the editor.
> 
> From here, click the three dots in the upper right and choose **Open file**
> 
> Browse to your new `Adventure` folder and choose `hello.sh`
> ![Acode Open File](AcodeOpenFile.jpg)

> Now, in the editor, write some Bash code!
> 
> Write the following:
> ```shell
> echo "hello world"
> ```
> And then tap the 💾 icon to save the file.
> ![Acode Hello Script](AcodeHelloWorld.jpg)

> _Next, we will run this Bash script with Termux!_

# Termux

![Termux Logo](TermuxLogo.png)

[Termux](https://termux.com/) is a free Android application which provides a lovely terminal with a Linux environment including Bash right on your Android phone or tablet.

> The [Termux Wiki](https://wiki.termux.com/wiki/Main_Page) has lots of great documentation!

1. [Install Termux](https://play.google.com/store/apps/details?id=com.termux&hl=en_US&gl=US) from the [Google Play Store](https://play.google.com/store/apps/details?id=com.termux&hl=en_US&gl=US)
2. Open **Termux**
3. You will be presented with a black screen with a `$` prompt.
	- **Termux** needs permission to access the **Internal storage/Adventure** folder.
	- To give **Termux** access, type the following, followed by the return key <kbd>⏎</kbd>
	   ```shell
	   termux-setup-storage
	   ```
4. Now, browse to the `Adventure` folder and run `hello.sh`!

> Run `termux-setup-storage`
> ![Termux Setup Storage](TermuxSetupStorage.jpg)

> Allow access to files
> ![Termux Allow File Folder Access](TermuxAllow.jpg)

> To get to the `Adventure` folder, browse to `storage/shared/Adventure` using the change directory (`cd`) command.
>
> Once there, run the `hello.sh` script via: `bash hello.sh`
>
> You will see the output: `hello world`
> ![Termux Hello World](TermuxHelloWorld.jpg)