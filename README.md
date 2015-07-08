- [Learn Version Control with Git](#)
	- [Section 0: Installing Git and Setup](#installing)
		- [0.1 On Windows](#windows)
		- [0.2 On Mac](#mac)
		- [0.3 First time git setup](#setup)
		- [0.4 Installing Sublime](#sublime)
	- [Section 1: Getting started with HTML](#html)
		- [1.1 Creating an HTML file](#createHtml)
		- [1.2 Adding content to our index.html](#addContent)
		- [1.3 Making changes to our index.html](#makeChange)
	- [Section 2: Introducing Git](#git)
		- [2.1 Staging files](#staging)
		- [2.2 Committing files](#committing)
		- [2.3 Checking the Git commit history](#log)
		- [2.4 Exercise Breakout](#exercise)
	- [Section 3: Adding your code to GitHub](#)
	- [Section 4: Working Together from an Existing Repository](#)
		- [4.1 Getting the Code](#)
		- [4.2 Git Workflow](#)
		- [4.3 Adding Content to the Blog](#)
			- [4.3.1 Adding a new HTML page](#)
			- [4.3.2 Adding Content to the new HTML page](#)
			- [4.3.3 Dealing with Merge Conflicts](#)
			- [4.3.4 Adding Images](#)

# Learn Version Control with Git

<a name="installing"/>
## Section 0: Installing Git and Setup

<a name="windows"/>
#### 0.1 On Windows 

Navigate to https://git-scm.com/download/win . This should automatically start a git download. Go through the git setup wizard steps and click finish when you get to the end of the installer.

Git should now be installed. You can verify by going to your desktop, right click and select ```git bash ```. This will open up a terminal window.

In the git-bash terminal window you can type:

```bash
$ git --version
```

If git is properly installed this command will tell you the version of git on your computer.

<a name="mac"/>
#### 0.2 On Mac

You will need to install [Xcode developer tools](https://developer.apple.com/downloads/) if you don't already have it installed. Sign in with your apple id and agree to the terms and conditions. Once you are on the downloads page, choose the ```Command Line Tools``` download and click on the ```.dmg``` file to start the download. Once it is done downloading, you can open the *DMG* and run the Command Line Tools installer.

Now we need to install git.

Navigate to http://git-scm.com/download/mac . This should automatically start a git download. Once it is done downloading, open the download and double click the *.pkg* file. Click through the steps of the package installer. 

When this is done, you can open the ```Terminal``` program and type in the command line:

```bash
$ git --version
```

If git is properly installed this command will tell you the version of git on your computer.

**Note**: If you get the error ```Agreeing to the Xcode/iOS license requires admin priviledges, please re-run as root via sudo```, then open up Xcode and accept the license agreement.

<a name="setup"/>
#### 0.3 First time git setup

Now that git is properly installed, let's set up our git identity. We can set our user name and e-mail using the following two commands:

```bash
$ git config --global user.name "Amber Houle"

$ git config --global user.email amber.houle3@gmail.com
```

<a name="sublime"/>
#### 0.4 Installing Sublime

We will be writing our code in the text editor Sublime throughout this workshop. If you don't already have Sublime installed you can go ahead and install it [here](http://www.sublimetext.com/2).

## Section 1: Getting started with HTML

#### 1.1 Creating an HTML file

Let's start by creating a basic HTML file on our computer. 

Open up your terminal and execute the following command:

```bash
$ cd ~/Desktop
```

**Note:** Your terminal is just a program that allows you to run different commands. In this workshop we will be using it to run [Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) commands. Bash is a command language that allows you to execute different commands through your terminal that interact with your computer.

```cd``` is a Bash command that allows you to change directories. In this case we are changing directories to our desktop directory.

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
		<title>Hello World</title>
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
		<title>Hello World</title>
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

#### 2.4 Exercise Breakout

Now that you know some of the git basics, let's add an image to our basic HTML page and commit that to our local git repository.

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

We are going to switch gears a little and work off of an existing HTML project we have created for this workshop. Let's split up into groups of 2 or 3. We will be working from the **wwc-basic-blog** repository at the top of this tutorial.

#### 4.1 Getting the Code

We will want to start by making a copy of [this code](https://github.com/msvivianso/wwc-basic-blog) into our own Github account. At the top right corner of the project page you will see a button that says *Fork*.

Go ahead and click on *Fork*. This will copy the code from Vivian's Github account to your own Github account.

Now within your group of 2 or 3 people, choose one Github account to work off of together. You will then need to add your team members as collaborators to your Github project. Navigate to the **wwc-basic-blog** project, click on *Settings* on the right hand side, and then click *Collaborators* on the left. Search for your team members by their Github username and add them to the project as collaborators.

To get the code from an existing project onto your computer you can use the ```git clone``` command. Before cloning the project, let's go back to our terminal and change directories back to our Desktop.

```bash
$ cd ~/Desktop
```

To clone the project, you need to specify the url of the project you are copying to your computer, for example:

```bash
$ git clone https://github.com/msvivianso/wwc-basic-blog.git
```

Cloning makes a copy of the project onto your computer. From now on, everyone in a team should be working from the Github project you added collaborators to. 

Go to your Desktop, open the **wwc-basic-blog** folder and double click the *index.html* file to open it in the browser.

#### 4.2 Git Workflow

We are going to go through and add some content so this basic blog page. We will use git as we go along to version and keep track of our changes.

When you are working with a team, it is good to get in the habit of following an agreed upon git workflow. For the remainder of this workshop, you should follow this git workflow when making changes to your code:

- make some changes to your code
- git status
- git add < filename >
- git status
- git commit -m "Message describing your changes"
- git pull
- git push

#### 4.3 Adding Content to the Blog

##### 4.3.1 Adding a new HTML page

Let's add a page to our blog and let's do this first part on one computer together in our teams. First, lets open the project in Sublime. You should see a folder called assets, an index.html file and a README.md. Now go to your terminal and make sure you are in the directory of the blog. If you want to check the current directory you are in you can type:

```bash
$ pwd
```

```pwd``` is another bash command that will show you your *present working directory*. You should be in the directory ```~\Desktop\wwc-basic-blog```. If you are not here then you can change directories:

```bash
$ cd ~\Desktop\wwc-basic-blog
```

Now let's create a new page for our blog so we can write about our favorite restaurants in Chicago. Remember the ```touch``` command allows you to create a new file:

```bash
$ touch favorite-restaurants.html
```

Let's go ahead and open the *favorite-restaurants.html* file in Sublime and add the basic HTML structure.

```bash
<!DOCTYPE html>
<html>
	<head>
		<title>Favorite Restaurants</title>
	</head>
	<body>
	</body>
</html>
```

If we want to use the same styling as our blog's front page we can include the *css* stylesheet called *main.css* which you can find in the *assets/stylesheets* folder. To include a *css* stylesheet you need to use the ```<link>``` tag and include it within the ```<head>``` tags of your HTML:

```bash
<!DOCTYPE html>
<html>
	<head>
  		<title>Favorite Restaurants</title>
  		<link rel="stylesheet" href="assets/stylesheets/main.css">
	</head>
	<body>
	</body>
</html>
```

```href``` specifies the location of the css stylesheet you are including in your HTML file. If you open the *favorite-restaurants.html* file in your browser, you should see a blank page. Let's go ahead and add a section to our new page with a header called *Favorite Restaurants in Chicago*: 

```bash
<!DOCTYPE html>
<html>
	<head>
  		<title>Favorite Restaurants</title>
  		<link rel="stylesheet" href="assets/stylesheets/main.css">
	</head>
	<body>
	    <section>
      		<h1>Favorite Restaurants in Chicago</h1>
    	</section>
	</body>
</html>
```

If you refresh the page in your browser you should now see the title *Favorite Restaurants in Chicago*.

This is a good point to *commit* your changes to your git repository and share your code with team members so that everyone can access these changes from their computers!

**Note:** Refer to section **4.2 Git Workflow** to remember the steps involved in committing your code to git and pushing your changes to Github.

Following this workflow, let's first check the current status of our git repository:

```bash
$ git status
```

We should see that we have an un-tracked file *favorite-restaurants.html*:

```bash
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	favorite-restaurants.html
```

We want to track this file and add it to staging:

```bash
$ git add favorite-restaurants.html
```

If we check the status again we can see which changes are ready to be committed:

```bash
$ git status
```

Now we can go ahead and commit those changes:

```bash
$ git commit -m "[Team Members Name] Adding a new HTML page for my favorite restaurants"
```

Our new file *favorite-restaurants.html* is now saved in our local git repository. We want to be able to share these changes with our team members and push the changes to Github. Before we push our changes, let's pull from Github to make sure our local project is up-to-date:

```bash
$ git pull 
```

Now that we know we have all of the most recent code from Github, we can push up our changes:

```bash
$ git push
```

If you refresh your Github project page you should be able to see your new *favorite-restaurants.html* file.


##### 4.3.2 Adding Content to the new HTML page

Your team should have completed *section 4.3.1* together on one computer. Now let's do some work on the same code base but from each of our own computers.

Remember, before you start making changes to the code, you should pull from Github to make sure you have all of the most recent changes:

```bash
$ git pull
```

Now all of your team members should have the new *favorite-restaurants.html* file on your computer.

Each team member should now add a section with a header containing one of their favorite restaurants in Chicago. For example:

```bash
<!DOCTYPE html>
<html>
	<head>
  		<title>Favorite Restaurants</title>
  		<link rel="stylesheet" href="assets/stylesheets/main.css">
	</head>
	<body>
		.
		.
		.

	    <section>
      		<h3>The Purple Pig</h3>
    	</section>

    	. 
    	.
    	.

	</body>
</html>
```

You should then follow the git workflow to commit your changes to your local git repository then push them to Github.

**Note:**

##### 4.3.3 Dealing with Merge Conflicts

What happens if two team members are making changes to the same file on the same line of code? How does git decide which change is correct and how to merge those changes together?

When you pull in code that has changes on the same line you have changed, git will give you a *merge conflict*. When this happens, you will need to open the file that has a merge conflict and manually choose which changes you want to be applied to the file.

##### 4.3.4 Adding Images

Each one of you should now find an image of your favorite restaurant, or favorite food on the menu, and add the image beneath the name of your favorite restaurant. You can use the example in the *index.html* file of how to add an image.

Once you've added your image, commit your changes and push them to Github.

