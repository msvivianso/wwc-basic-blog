# Learn Version Control with Git

## Section 0: Installing Git

#### On Windows

Navigate to https://git-scm.com/download/win . This should automatically start a git download. Go through the git setup wizard steps and click finish when you get to the end of the installer.

Git should now be installed. You can verify by going to your desktop, right click and select ```git bash ```. This will open up a terminal window.

You can type:

```bash
$ git --version
```

If git is properly installed this command will tell you the version of git on your computer.

## Section 1: Getting started with HTML

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

#### Adding content to our index.html

Let's go to the bottom right corner of Sublime. We should be able to click and choose the language we are using, so go ahead and select HTML from the list of languages.

Let's start by creating the base of our HTML file. In your index.html file, add the following code:

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
		<p>Hello World!</p>>
	</body>
</html>
```

Navigate to the **women-who-code** folder on your desktop and double-click the index.html file to open it in your browser. You should see the *Hello World!* message in your browser.

Now let's make a change to our index.html. Instead of saying *Hello World!* say hello to the person sitting on your right. For example *Hello Vivian!*

Your code should now look something like this:

```bash
<!DOCTYPE html>
<html>
	<head>
		<title></title>
	</head>
	<body>
		<p>Hello Vivian!</p>>
	</body>
</html>
```
Refresh your browser to see the new message.
