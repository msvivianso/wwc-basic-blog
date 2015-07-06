# Learn Version Control with Git

## Installing Git

### On Windows

Navigate to https://git-scm.com/download/win 

This should automatically start a git download

Go through the git setup wizard steps and click finish when you get to the end of the installer

Git should now be installed

You can verify by going to your desktop, right click and select ```bash git bash ```

This will open up a terminal window

You can type

```bash
$ git --version
```

If git is properly installed this command will tell you the version of git on your computer

## Getting started with HTML

Let's start by creating a basic HTML file on our computer. 

Open up your terminal and execute the following command.

```bash
$ cd ~/Desktop
```

**cd** is a bash command that allows you to change directories. In this case we are changing directories to our desktop directory.

Now let's create a new directory called **women-who-code**. We can do this by using the **mkdir** command as shown below.

```bash
$ mkdir women-who-code
```
We can then change directories to the **women-who-code** directory using by running:

```bash
$ cd women-who-code
```

Now let's create a new file in our women-who-code directory. The bash command ***touch*** will allow you to create a new file. Let's create a file called **index.html**:

touch index.html

If you go to your Desktop, you should see the women-who-code folder with the index.html file inside. 

Go ahead and open this file in the text editor Sublime.
