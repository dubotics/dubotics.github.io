---
title: Using Git
layout: general
parent: /resources.html
---

## What is Git?

When teams want to collaborate in writing code, they often run into two problems:

1.  How to make sure everybody's working with the latest, most-updated version of the code
2.  How to keep track of old versions of files, so we can revert in case somebody makes a 
    mistake while writing a file.
    
"Version control" software is designed to solve these two problems. Every kind of version
control software (in some way) consists of a central server that hosts our code, and a 
method of allowing developers to grab and update that central code. 

The specific name of the version control software we're using is called "git". Currently, 
all our code is hosted on <https://github.com/dubotics>.

If you want to help write code, you need to know how to use Git. Here's a step-by-step guide
to getting started.

1.  [Get a github account](#get-account)
2.  [Install Git](#install-git)
3.  [Test your installation](#test-installation)
4.  [Download a copy of the code](#download-repo)
5.  [Commit changes](#commit-changes)
6.  [Test it out!](#test-it-out)

<h2 id="get-account">1: Get a github account</h2>

Make an account at <http://github.com>. It'll ask for your email -- you should 
probably use your primary email (not your UW one) so you can continue to use Github after you
leave UW.

Once you have an account, <a href="mailto:michael.lee.0x2a@gmailcom">email me</a> your username
so I can add you to the "dubotics" organization.


<h2 id="install-git">2: Install Git</h2>

You can download Git at these links:

-   **Windows**: <http://git-scm.com/download/win>
-   **Mac**: <http://git-scm.com/download/mac>
-   **Linux**: <http://git-scm.com/download/linux>

The installer will ask you to configure a few things. Accept all the default options, and keep clicking 'next'. 

If you use Windows, you will need to add "git" to your path so you can use it from the command line.
Do the following:

1.  Windows 8:
    1.  Go to the start screen, and type "Edit the system environment variables". Make sure to
        search under "settings", if you don't own Windows 8.1
    2.  Click the option that appears
2.  Not Windows 8:
    1.  Right-click on "My Computer"
    2.  Click "Advanced System Settings" from the left
3.  Click "Environment Variables" in the bottom of the window
4.  Under "System Variables" look for the "path" variable. Click it to highlight it, 
    and click the "edit" button.
5.  At the very end, add `;C:\Program Files (x86)\Git\cmd` (don't forget the semicolon 
    at the beginning)
6.  Save and exit


<h2 id="test-installation">3: Test your installation</h2>

Before we move on, let's make sure we installed git correctly.

-   **Windows 8:** Go to the start screen, and type "Powershell". Open the program.
-   **Not Windows 8:** Click "start", and type "Powershell" inside the "run" textbox. 
    Open the program.
-   **Macs:** Open the console/command line/terminal whatever the hell it's called.
    I don't own a mac, so idk where it's located (it might be under /Applications/Utilities)
-   **Linux:** Open the console/terminal.

Type in `git`. A bunch of text should appear, displaying usage information. If your console 
says it could not locate git, stop, and <a href="mailto:michael.lee.0x2a@gmail.com">email me</a>. 
Something has gone wrong.


<h2 id="download-repo">4: Download a copy of the code</h2>

Each project is stored in their own "repository". We currently have two -- one for 
[the robot](https://github.com/dubotics/robocrisp-robot) and another for 
[the base station](https://github.com/dubotics/robocrisp-base). We're now going to grab a 
copy of both.

Within your terminal, navigate to the folder you want to put your copy of the two repos in.

-   Type `ls` to see a list of all files in your current folder
-   Type `cd ..` to go up one folder
-   Type `cd folder_name` to go into that folder

Once you're at your current location, type in:

```bash
git clone https://github.com/dubotics/robocrisp-base.git
git clone https://github.com/dubotics/robocrisp-robot.git
```

This will download the two repositories into two folders named `robocrisp-base` and `robocrisp-robot`. You will need to do this only once.


<h2 id="commit-changes">5: Commit changes</h2>

Git allows you to do all sorts of wild and zany things. In the interests of keeping things simple, I'm only going to teach you four commands. 

Make sure you're inside the repo folder in your terminal before running these commands.
For example, if I edited something inside the `robocrisp-base` folder, your terminal should look like one of the following, depending on which operating system you use:

```bash
C:\Users\Name\Documents\DUBotics\robocrisp-base>
user@computer ~\DUBotics\robocrisp-base $
```

So, here are the four commands:

```bash
git pull origin master
git add -A
git commit -m "Add a description of what changes you made here"
git push origin master
```

The very first line updates your code to the latest version. Always do this BEFORE you start
editing code. If you don't, bad things can happen, and it'll be a pain to fix it.

Once you **pull** the latest changes, you can edit your files. If you're using Windows, you can
always use Notepad. Notepad is kinda bad though, so I prefer using 
[Notepad++](http://notepad-plus-plus.org/), but it doesn't matter which text editor you use. Use whatever you like. 

If you're using Mac/Linux, I'm assuming you have a decent editor bundled by default you can use.

Once you've finished editing your code, save any changes and type the next three lines. 

The second line adds any new files you might have made to the **commit**.
The third line "commits" your changes, and saves a description of _what_ changes you made.
The final line pushes all changes to github, so others can see it.

Got it? Your workflow should be something like:

1.  `git pull origin master`
2.  Make and save changes
3.  `git add -A`  
    `git commit -m "I changed X to do Y because of Z"`  
    `git push origin master`
4.  Goto step 2


<h2 id="test-it-out">6: Test it out!</h2>

Let's make sure everything works!

1.  Download the two repos, if you haven't already
2.  Navigate to the `robocrisp-base` folder using the terminal.
3.  Update the repo (`git pull origin master`)
4.  Open the `README.md` file using a text editor of your choice
5.  Under the `contributors` section, add your name and your github username. My name should be up there -- use that as an example of how to format it.
6.  Save the file
7.  Push your changes to the repo (be sure to customize the commit message):  
    `git add -A`
    `git commit -m "Testing: I added 'bob bobbly' as a contributer"`  
    `git push origin master`
8.  Repeat steps 2 - 7 for the `robocrisp-robot` repo

Now, if you navigate to <https://github.com/dubotics/robocrisp-base> or 
<https://github.com/dubotics/robocrisp-robot>, you'll see your changes in the readme!

You're done!




