To write and develop Bash applications on an iPad or iPhone, you will need two things:

1. **Text Editor** to write and edit Bash scripts ( _plain-text files_ )
1. **Bash** ( _e.g. a Linux environment running on iOS with Bash_ )

As of 2021, there is really only one good option for running **Bash** on Android: [[#iSH]]

There are _multiple_ text editors available, but I recommend [[#Textastic]] because I found it integrated well with [[#iSH]] (_and the [Files app](https://support.apple.com/en-us/HT206481)_)
 
 
The following instructions will get you up-and-running with Bash on your iOS device!

- [[#Textastic]] Text Editor (_with Bash support!_)
- [[#iSH]] Linux Environment (_with Bash!_)

# Textastic

There are _**lots**_ of code editors available for iOS.

To write Bash code on your iOS device, the _most important feature_ of any Text Editor is: **integration with the [Files app](https://support.apple.com/en-us/HT206481)**.

This is because [[#iSH]] provides great integration with the Files app.

I tried a few popular editors as of 2021 and found [Textastic](https://www.textasticapp.com/) to provide the best experience for Bash.

> As of 2021, **Textastic** costs $10 USD.
>
> I _really_ wanted to like [Koder Code Editor](https://koderapp.com/) (_which is free_) *but, as far as I can tell, you cannot **create** files in any locations provided by the Files app.*

1. [Purchase and Install Textastic](https://apps.apple.com/us/app/id1049254261?mt=8) from the [App Store](https://apps.apple.com/us/app/id1049254261?mt=8)
2. Proceed to the [[#iSH]] step below to setup Bash + Textastic!

# iSH

[iSH](https://ish.app/) is really lovely.

It provides an [Alpine Linux](https://alpinelinux.org/) environment in your iPhone or iPad.

> By default, **iSH** uses the [Almquist](https://en.wikipedia.org/wiki/Almquist_shell) (or `ash`) shell.
> But Bash can be _easily_ installed!

1. [Install iSH Shell](https://apps.apple.com/us/app/ish-shell/id1436902243) from the [App Store](https://apps.apple.com/us/app/ish-shell/id1436902243) (Free)
2. Open the **Files** app and enable the **iSH** Files provider.
3. Install Bash
4. Proceed to [[#Hello Bash]] to set Bash as your default shell and write your first Bash _"Hello, world!"_ script on your iOS device!

---

> Open the `Files` application
> ![Files App](FilesApp.png)

> Edit available `Files` locations by clicking the three dots in the upper right
> ![Edit Files](FilesAppEdit.png)

> Enable the **iSH** Files location provider by toggling the toggle to the right
> ![Enable iSH Files](FilesAppiSH.png)

> Open **iSH**

> Install **Bash** by running `apk add bash`
> ![iSH Install Bash](iSHInstallBash.png)

> Proceed to [[#Hello Bash]]

# Hello, Bash!

With both a **Text Editor** and **Bash** installed, you're nearly ready for adventure!

1. ( _Optional_ ) Set Bash as default iSH shell
2. Create a _"Hello, world!"_ script
3.  Run _"Hello, world!_ script!

## Set Bash as Default Shell
_( Optional )_

You probably want the iSH terminal to use Bash!

By default, it uses `ash` shell. To confirm this:

1. Open **iSH**
2. Type `echo $SHELL` followed by the return key <kbd>⏎</kbd>
  ```shell
   echo $SHELL
   # => /bin/ash
   ```
3. Shells are configured per user, so get the name of your user:
  ```shell
   echo $USER
   # => root
   ```
4. Get the path of the Bash shell to configure it as the default:
  ```shell
   which bash
   # => /bin/bash
   ```
	
Next, use **Textastic** to configure the default shell to Bash.

Users' default shell are configured in the `/etc/passwd` file.

You will use **Textastic** to:
1. Open the `/etc/passwd` file
2. Change `/bin/ash` to `/bin/bash` for the `root` user
3. Save the file
4. Open a new iSH session and confirm that Bash is now the default shell!

> Open **Textastic**
> ![](TextasticStart.png)

> Click the `< Textastic` left arrow to go to the **Textastic** browser
> ![](TextasticBrowse.png)

> Tap "Open" and then tap on the **iSH** location
> ![](TextasticiSH.png)

> Tap on the `etc` folder to navigate to view the files in the `etc` folder of **iSH**
> ![](TextasticFolders.png)

> Tap on the `passwd` file to open it for editing
> ![](TextasticPasswd.png)

> Take a look. See how the first line says `root` and then `/bin/ash`? That's what we're going to edit!
> ![](TextasticEditPasswd.png)

> Tap on the file text and use the keyboard to change `/bin/ash` on the first line to `/bin/bash`
> ![](TextasticConfigureBash.png)

> Then, to save the file, close the keyboard by tapping the keyboard close button (_upper right of the keyboard_) and then tap on the `< Textastic` back button in the upper left of the application
> ![](TextasticSavePasswd.png)

> That's it! Now start a new **iSH** session and check that it worked!
>
> _You can end your currently open **iSH** session by typing `exit` followed by the return key <kbd>⏎</kbd>_

> In a new **iSH** session, check the default shell by typing `echo $SHELL` followed by the return key <kbd>⏎</kbd>
> ![](iSHDefaultShell.png)

> Proceed to the next section to [[#Create Hello world Script]]

## Create "Hello, world!" Script

By default, **iSH** will always open to `/root` folder.

So let's create a new folder in the `/root` folder. We'll name it `Adventure`.

Inside that new folder, we will create a `hello.sh` Bash script file.

There are a few ways that you can create the new `Adventure` folder:
1. In **iSH** simply run the command `mkdir Adventure`
2. Use the **Files** application to make the folder
3. Use the **Textastic** application to make the folder

Here, you can see using the **Files** application:

> In the **Files** application, browse to **iSH**
> ![](FilesAppBrowse.png)

> Choose **iSH** to browse folders in **iSH**.
> Tap on the `root` folder, where we will make a new `Adventure` folder.
> ![](FilesAppGotoRoot.png)

> Tap the three dots in the upper right and choose **"New Folder"**
> ![](FilesAppNewFolder.png)

> Name the new folder `Adventure`
> ![](FilesAppAdventureFolder.png)

> Now open up **Textastic**

> From the **Textastic** browser, choose **"Create External File..."**
> ![](TextasticBrowse.png)

> Name the new file `hello.sh`
> ![](TextasticNewFile.png)

> Tap **"Choose Location"** and browse to the new `Adventure` folder in in the `root` folder of **iSH**
> ![](TextasticChooseLocation.png)

> Tap **"Move"** and then press **"return"**

> Tap into the editor of this new, empty file, and type:
> ```sh
> echo "hello world"
> ```
> ![](TextasticWriteHelloWorld.png)

> Close the keyboard and tap the `< Textastic` back button to save the file

> Proceed to [[#Run Hello world Script]]

## Run "Hello, world!" Script

1. Open **iSH**
2. Go to the new `Adventure` folder
3. Run the `hello.sh` Bash script!

> ![](iSHRunHelloWorld.png)