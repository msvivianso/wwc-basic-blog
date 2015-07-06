# Learn Version Control with Git

## Section 0: Installing Git

#### 0.1 On Windows

Navigate to https://git-scm.com/download/win . This should automatically start a git download. Go through the git setup wizard steps and click finish when you get to the end of the installer.

Git should now be installed. You can verify by going to your desktop, right click and select ```git bash ```. This will open up a terminal window.

In the git-bash terminal window you can type:

```bash
$ git --version
```

If git is properly installed this command will tell you the version of git on your computer.

#### 0.2 First time git setup

Before we get started, let's set up our git identity. We can set our user name and e-mail using the following two commands:

```bash
$ git config --global user.name "Amber Houle"

$ git config --global user.email amber.houle3@gmail.com
```

## Section 1: Getting started with HTML

#### 1.1 Creating an HTML file

Let's start by creating a basic HTML file on our computer. 

Open up your terminal and execute the following command:

```bash
$ cd ~/Desktop
```

```cd``` is a bash command that allows you to change directories. In this case we are changing directories to our desktop directory.

Now let's create a new directory called **women-who-code**. We can do this by using the ```mkdir``` command as shown below.

```bash
$ mkdir women-who-code
```
We can then change directories to the **women-who-code** directory by running:

```bash
$ cd women-who-code
```

Now let's create a new file in our women-who-code directory. The bash command ```touch``` will allow you to create a new file. Let's create a file called **index.html**:

```bash
$ touch index.html
```

If you go to your Desktop, you should see the women-who-code folder with the index.html file inside. Go ahead and open this file in the text editor Sublime.

#### 1.2 Adding content to our index.html

Let's go to the bottom right corner of Sublime. We should be able to click and choose the language we are using, so go ahead and select HTML from the list of languages.

Now, let's start by creating the base of our HTML file. In your index.html file, add the following code:

```bash
<!DOCTYPE html>
<html>
	<head>
		<title></title>
	</head>
	<body>

	</body>
</html>
```

Within the ```<body>``` tag, let's add a paragraph with the text *Hello World!*. Your file should now look something like this:

```bash
<!DOCTYPE html>
<html>
	<head>
		<title></title>
	</head>
	<body>
		<p>Hello World!</p>
	</body>
</html>
```

Navigate to the **women-who-code** folder on your desktop and double-click the index.html file to open it in your browser. You should see the *Hello World!* message in your browser.

#### 1.3 Making changes to our index.html

Now let's make a change to our index.html. Instead of saying *Hello World!* say hello to the person sitting on your right. For example *Hello Vivian!*

Your code should now look something like this:

```bash
<!DOCTYPE html>
<html>
	<head>
		<title></title>
	</head>
	<body>
		<p>Hello Vivian!</p>
	</body>
</html>
```
Refresh your browser to see the new message.

## Section 2: Introducing Git

Let's add version control to our project with Git! To initialize a new git repository for your project, make sure you are in the **women-who-code** folder and type

```bash
$ git init
```

This will create a .git directory, which is where git does all of its work and stores all the history of your project. To see the .git directory, in the terminal we can type:

```bash
$ ls -a
```

```ls``` is another bash command that will list all of files and folders in your current directory. The option ```-a``` will make sure you list all of the files and folders, including the .git directory.

#### 2.1: Staging files

A really useful command is to check the status of your git repository. This will tell you what files you have modified and which files are in staging ready to be committed. To check the status of your git repository you can type:

```bash
$ git status
```

The output of git status should tell you that your *index.html* is untracked. This means you aren't yet tracking your index.html with your version control system.

To start tracking your *index.html* we can run the command:

```bash
$ git add index.html
```

The ```git add``` command will move your index.html file from your working directory to staging. Staging is like a holding place for all of your changes before you save them to the git repository. The ```git add``` command takes the filename as an argument in the format ```git add <filename>``` so that you can specify which files you want to add to staging.

If we check the git status again, we can see that the index.html file is in staging and ready to be committed.

#### 2.1: Committing files

We have moved our changes from the working directory to staging, but these changes won't be saved in our version control history until we commit them to the git directory. In git, the term *commit* is just another way of saying *save* our changes to the git directory. 

To commit our staged files we can run the command:

```bash
$ git commit --message "Useful message describing the changes you are committing"
```

Now if we check the ```git status``` again we will see that there is nothing to commit. Our working directory doesn't have any new changes.

#### 2.1: Checking the Git commit history

If we want to see a list of all the commits we have made we can use the command:

```bash
$ git log
```
The output of ```git log``` will show you a list of commits in your git history. For each commit you can see the author of the commit, the date you committed the changes, the commit message as well as the commit id. The commit id is a unique identifier used by git that allows you to view and refer to specific commits in your git history.









