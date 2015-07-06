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

Now let's create a new directory called **women-who-code**. We can do this by using the ```mkdir``` command as shown below:

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

Now let's make a change to our index.html. Instead of saying *Hello World!* say hello to the person sitting on your right (or left). For example *Hello Vivian!*

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

#### 2.1 Staging files

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

#### 2.2 Committing files

We have moved our changes from the working directory to staging, but these changes won't be saved in our version control history until we commit them to the git directory. In git, the term *commit* is just another way of saying *save* our changes to the git directory. 

To commit our staged files we can run the command:

```bash
$ git commit --message "Useful message describing the changes you are committing"
```

Now if we check the ```git status``` again we will see that there is nothing to commit. Our working directory doesn't have any new changes.

**Note**: To include a commit message, you can use the option ```--message``` as seen above. Alternatively you can use the option ```-m``` which is just a shorthand notation for ```--message``` in which case your commit would look like:  ```git commit -m "Useful commit message"```

#### 2.3 Checking the Git commit history

If we want to see a list of all the commits we have made we can use the command:

```bash
$ git log
```

The output of ```git log``` will show you a list of commits in your git history. For each commit you can see the author of the commit, the date you committed the changes, the commit message as well as the commit id. The commit id is a unique identifier used by git that allows you to view and refer to specific commits in your git history.

## Section 3: Adding your code to GitHub

What if we want to store all of our code in a centralized location? We can move our project to GitHub, which is a git repository hosting service. To add our code to Github, we will first need to create a new repository (or project).
- Navigate to your github profile
- Click on the *Repositories* tab
- Click the green *New* button to create a new project
- Enter a name for your project where it says *Repository name*
- Click the green *Create Repository* button

You have already created a git repository on your computer, so now we just need a way of linking your local git repository with your Github account. To do this, in the terminal we can execute the command:

```bash
$ git remote add origin <github project url>
```

You can find your ```github project url``` on the Github project page once you have created a new repository.

In git, ```remote``` just refers to a "remote" location where your code exists, a centralized location somewhere other than your own computer. In this case the remote is referring to Github. By running the above command, we are adding a remote location called ```origin``` which points to the project url in Github.

To then add our code to our remote location in Github we can run the following command:

```bash
$ git push -u origin master
```

This promotes your code from your local computer to your project created in Github. The ```-u``` option sets the ```git push``` command to push your code to the ```origin``` from ```master```. ```origin``` is the name we gave to our remote repository in Github and ```master``` is just a name referring to the git repository we are working from on our own computer.

If we refresh our Github project page, we should now see our code has been added to Github!

## Section 4: Working Together from an Existing Repository

We are going to switch gears a little and work off of an existing HTML project we have created for this workshop. Let's split up into groups of 2 or 3. We will be working from the wwc-basic-blog repository at the top of this tutorial.

#### 4.1 Getting the Code

We will want to start by making a copy of [this code](https://github.com/msvivianso/wwc-basic-blog) into our own Github account. At the top right corner of the project page you will see a button that says *Fork*.

Go ahead and click on *Fork*. This will copy the code from Vivian's Github account to your own Github account.

Now within your group of 2 or 3 people, choose one Github account to work off of together. You will then need to add your team members as collaborators to your Github project. Navigate to the **wwc-basic-blog** project, click on *Settings* on the right hand side, and then click *Collaborators* on the left. Search for your team members by their Github username and add them to the project as collaborators.

To get the code from an existing project onto your computer you can use the ```git clone``` command. Before cloning the project, let's go back to our terminal and change directories back to our Desktop.

```bash
$ cd ~/Desktop
```

You need to specify the url of the project you are copying to your computer, for example:

```bash
$ git clone https://github.com/msvivianso/wwc-basic-blog.git
```

From now on, everyone in a team should be working from the Github project you added collaborators to.

Go to your Desktop, open the **wwc-basic-blog** folder and double click the *index.html* file to open it in the browser.

#### 4.2 Making Changes

#### 4.3 Git Workflow

When you are working with a team, it is good to get in the habit of following an agreed upon git workflow. For the remainder of this workshop, you should follow this git workflow when making changes to your code:

- git pull
- make some changes to your code
- git status
- git add <filename>
- git commit -m "Message describing your changes"
- git pull
- git push