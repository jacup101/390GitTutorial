# How To Git
by Joshua Pulido

## What is Git?

Simply put, Git is a software that allows for version control of files, a feature that is particularly helpful when working with code. The following tutorial will outline some of the many commands in simple detail, for a quick start, but there are many powerful tools not mentioned here that make git very useful to learn.

__Table of Contents:__
1. [Getting Started](#getting-started)
	* [Installation](#installation)
	* [On To Terminal](#on-to-terminal)
2. [Cloning Repositories](#cloning-repositories-git-clone)
3. [Creating A Git Repository](#creating-a-git-repository)
4. [Initializing A Local Repository](#initializing-a-local-repository)
5. [Adding, Committing, and Pushing](#adding-committing-and-pushing)
6. [Pulling Code](#pulling-code)
7. [Branches (git branch)](#branches-git-branch)
8. [Merging Branches (git merge)](#merging-branches-git-merge)
	* [Merge Conflicts](#merge-conflicts)
9. [Stash (git stash)](#stash-git-stash)

# Getting Started

While there are many methods for using Git, it is most beneficial to learn through the use of the command line, as it provides for full access to all of Git’s tools. To start, first create a Github account at this link [here](https://github.com/join).

For full access to Git, you might also have to create a Personal Access Token, if you have not already done so. Detailed instructions for how to do that can be found [here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token).

### Installation

Next, lets install Git. On Windows, I would recommend installing Git Bash, as it allows for full parity with the Mac and Windows versions. The link to install can be found [here](https://git-scm.com/downloads), and this will install both Git and Git Bash, the necessary tools.

On Linux, installing is as simple as running: sudo apt install git-all.

![](https://lh6.googleusercontent.com/zZFuZOVOYs3kLow9ywRavDmnA0QK6U-BROMw-1273z_HXLrbbtpKc8ufuzDbB_vtKG3GtPJTqZtl7wbJiu6_fk1PzfxzYeNE7kE74hclZRIdD0MyNkQkmBzLsdQqXR_hkgjUfyFD)
On Mac, if you have homebrew installed, you can run brew install git. Informations for installing homebrew, as well as alternative install methods, can be found [here](https://git-scm.com/download/mac)

### On To Terminal
Once Git is installed, first check that it has successfully installed by running `git --version`, as shown in the screenshot below. It should output “git version X.XX.X”, depending on the version number.

![](https://lh4.googleusercontent.com/gyF7_Tl70wEEtTc8VUfOSaMjfJ_c01t5UhGjTy3CDiw3NxQyqOSa4P0bX-WxiY0RwprjZqKrDNyOv4gkkSAbWFF7jxraQWSdgGhefNzBT28TkFsPf9butoqe6HmHVPdRMNymaJ49)
Before we do anything with git, there are still a couple of setup steps. We’ll first tell git who we are by adjusting the configuration email and name, using the following commands.
```
git config --global user.name “your name”
git config --global user.email “youremail@domain.com"
```
![](https://lh5.googleusercontent.com/P3EdwspmaztmOuEIAi73DsJcty2V5hLKE2KRc1Zv4m7pGqQE9BlnFBOwq9JD_MT1CFJQifHhsr62IA1cd-c2xcUZ0x78evg7hiVa42BAqwL5rMoMIzmrkGaLPQb5d1gySajqma-1)

We’re now ready to start using Git! We’ll begin by learning the clone command first.

## Cloning Repositories (git clone)
The git clone command allows you to download any public repository to your local computer, where you can then contribute to the code do anything else you’d like. For this tutorial, we’ll clone [this repository](https://github.com/jacup101/gitTutorial) that contains some sample code:

We first obtain the Github clone link by clicking on the green “code” button, then copying the HTTPS url, as shown below in the screenshot.

![](https://lh5.googleusercontent.com/i-MAxrlSnzpzYrhsdwrJHc_Abf9SsQ7363w8ePx3-9_WbN0Q4x2DFSEzaQz71bG0cxBUGeOcKVbWRcyQKprJeAQcPpvM7SEJwjpbQzGhaemHTNcAPx7_2ReF9Z2v6-1xMpchsw5_)

Next, we will navigate to a directory of our choice using cd (change directory) in terminal. A popular directory might be the Documents folder, which you can get to by inputting the following command: `cd ~/Documents`

However, any directory will work. We will then run the following command:
```
git clone https://github.com/jacup101/gitTutorial.git
```
This will create a new directory, which we can see by running `ls`
We can also navigate into the directory by running `cd gitTutorial`
Running `ls` again shows that there is a README.md and a script.py file. We’ll now use these files to create a new git repository.

![](https://lh5.googleusercontent.com/iKXnTWz5w5CA-jVcLxgaVEW19YPT6D22pTXDE1tOsAg9o70OyW9UPQ4Yudo1f8RSm4pRNIy5403H61KUjmd7KtldFSwvFyxV0_Wgs8qa5eVGIB6SYoDk_VsYFWMNxkfenjJfbQuq)

## Creating a Git Repository

In order to create your own git repository, first sign in to github.com, if you have not done so already. Once signed in, you should be able to create a new repository by clicking the plus button in the top right corner, then “New Repository”.

![](https://lh3.googleusercontent.com/R2sxCEeY2hwPsI9Tvu5FeCuSMyVLBgiy-LQ8GdiuxVDKwU5lDhb1EKuNStTPi10saQ-p07A0ssBth3QJ87F34bgwORpzIBTidRMEw5V6X4adVndnIpy6sc35Uf7HcG9lIHjrMwOJ)

You can name the repository whatever you’d like, I’ll name it gitTutorial2. There are also other options, such as adding a README and .gitignore files; since we have a README file already, we’ll keep it unchecked for now, but these files are useful to any real project. Once you’re ready, click create repository.

![](https://lh5.googleusercontent.com/6BwKQOO0DemVOoFawcXpvB0oYTiOpuKgzsxFNlMXCbGoSlcozyHEs4ciMYZHtXggEbzbTqtrgX_7Vh8N0753knpg-SDa1b0Rt9ULNDyaQfmURdvU-oNFBYji39yP3inyoJXZDtKd)

We will also be removing the local repository we just cloned, but not the files we downloaded. To do this, let’s first run `ls -a` to show all files, including hidden ones, in our directory

You will notice that there is a hidden directory, called .git, which stores the local repository. To remove it, we can run `rm -rf .git` (The -rf is necessary to remove directories)

Now, running `ls -a` again, we see that the .git directory is gone. We have removed the old repository, and can now initialize a new one.

## Initializing A Local Repository

In order to initialize a local repository, we always first run

```
git init
```
This will create a new .git folder, with all the necessary information for a git repository.

We’ll also run the command below, replacing URL with your repository's git url, which for me is https://github.com/jacup101/gitTutorial2.
```
git remote add origin “URL”
```
This command connects our local repository to the remote repository we just created on Github. We have now successfully set up a local repository, which we can use to push code to our remote repository on Github.

## Adding, Committing, and Pushing
Currently, our remote repository has no files. We’ll change that by adding our two files, README.md and script.py, using git add as follows:
```
git add script.py
git add README.md
```
(We could also have added all files using git add -A, however this is not frequently used in practice as adding individual files is part of what makes version control so powerful.)

We will next commit our changes to the local repository, which will create a new “version” locally. It is standard to add a commit message as well using the -m option, which describes our changes. We will run the following command here:

```
git commit -m “Added the first files for this project”
```
For our first push, we will also create the main branch, as follows:
```
git branch -M main
```
This is not something that has to be done every time, but for the initial commit to an empty repository, it is necessary to make sure we're on the main branch.

Finally, we will push the changes to our local repository to the remote repository, by running:
```
git push origin main
```
![](https://lh5.googleusercontent.com/B9EbSdqTibYw27dIccKWQ31t9hu0g9LUqjk4angpUZsSr1kZ9agVfLyDFD_DRcCVgmvU0fD8zr_x1-IuwI14AU1-PgNL7xrp5JeNIXQuY8xWVj5BMcmLCFdHrtNlMl7Yv6cFSXmK)
Note that when pushing, you will be prompted for a username and password, which git uses to verify you have permissions to push to this remote repository. The username should be your github username, which for me is jacup101, and password is the __personal access token__ you created earlier, ***NOT your github.com password***. Also, your password will not show up when you type, but this is normal, just copy and paste your personal access token (ctrl-v or shift-insert), and then hit enter.

Now, if we check our github repository online, we should see our files on the main branch.
![](https://lh4.googleusercontent.com/fFjUQkHc7BdFH4P9MWyHU70ELgOg81APOCINjQc3LNByX0jOP7VijeGpoBvW3BQgJuSryYbg_yE9UEBfUfU9--Ox3uuODr-uMJ6cI_Y90Du5xVhSNYmIrCG6VvrZmG_PRhnff5up)

Next, we’ll cover how to pull changes to our code that others might make.

## Pulling Code
We’ll start off by editing the code on github.com. Navigate to your repository, click on script.py, and then click on the pencil to open the Github editor. We can change the Hello to Goodbye in the script, and do anything else. After adding a commit message describing your changes, click the commit changes button.

![](https://lh5.googleusercontent.com/4gNggwSfrfe7g7RLkY6HYr_lF9_7HybZfeNNUL0wIOedSR9e5yAblfowW4GIu24hwEdjhBpbZz6P36mSkRoWnCVbmms4BzEZcwV6yWM7TlqQr0Gkd6J9fos04XCKl1Ei0Ipn8AI6)

Now, we’ll pull those changes from the remote repository to our local repository, by using terminal to run the following command:
```
git pull origin main
```
If successful, running ```cat script.py``` will show the new script.
![](https://lh6.googleusercontent.com/mttD9kN-ceUo_F98l6NdK8WyEscpLlH8fuxMn_hjyOCy2xT7k-z9nREeYjkmHIiJ12vNEXS0UuFjk6wfdFQVmrJlmwYSN2bUwkFCcfB_ODaBgxb2-puP2-VizqH_fMF-Yp9MGPpq)

Now that we know the basic features of Github, we'll talk about some of the features that make it so powerful.
## Branches (git branch)

Often when working on a project, many features are being implemented at once, separate from each other. Branches make it easy to work on these experimental features, while also maintaining a single, main branch for all code that works properly. 

The diagram below shows how branches work, at a high level:

![](https://lh5.googleusercontent.com/DEFPLO-imwNk9wsg5IS2418pDJBipBOi0tUC-vRMZecLpNCtYEkeVXoB0i5JXg5UkS1UjbT95vfZsU-THWOeew1vZf47CRW1q6AYrYwKR4yvCXZts1VXQqTbxtmiTxZ5p2NsqINU)
<sub>Image credit: [nobledesktop.com](https://www.nobledesktop.com/learn/git/git-branches)</sub>

First, we will start by creating our own branch, using the git branch command. We will create a separate branch, called niceDay, to add a line that says “Have a nice day” after saying goodbye. We do so using the following commands:
```
git branch niceDay
git checkout niceDay
```
The git branch command creates the branch niceDay, and the git checkout command changes the current branch we are working on from main to our newly created niceDay branch. The `git checkout -b niceDay` shortcut could also be used, to only have to run a single command.
![](https://lh4.googleusercontent.com/QFwF9dgnB76sydhXOheLYk9J6p9VQ_od78GR_YLk-i2r30J4bRvOTrxN6PLIQqep4vdMrqPyfTepAK2FwQDi2AxG-wweaxANbd3gojYJtcD9Wd_iLOIi33rsUBMkZOIixioQX6MU)
Using your preferred text editor (I’ll use vim, but any other works), add the following lines of code to the beginning and end of script.py.
```
print(“Welcome to the Goodbye Program”)
...
print(“Have a nice day”)
```
![](https://lh3.googleusercontent.com/8Yu-ITA8axdehk5arW9Mm0m14JMxhMWKbJaw0eKR6yYGiSFS0nR6mwnz77ALFuAOfsnRdjMmxWhatOaZ_YCX7cmqTNXXqz43qpVMfm63EwfC_CsFxejLZ7FRGU916dyfgjquQR54)
Then, add, commit, and push the file, using the following commands like before.
```
git add script.py
git commit -m “Added nice day”
git push origin niceDay
```
Note that the main, from git push origin main earlier, is now niceDay, since we changed branches.
If we now navigate to our github repo in our browser, we should be able to see the new branch, by clicking on the branch dropdown menu and clicking on niceDay.

![](https://lh6.googleusercontent.com/Ei2hqCSZDAJJgRKjIXaXAeGo8WCjEouqZGUWGHzQhy3RJu-6_RqmxU670JhXE3ennpSFFHDq_0J5K8ldA1anCA75k_59LzFFUqA_xene9sdAgCfPk9nO-A70v-4jGcCT1_U4kwJA)
![](https://lh5.googleusercontent.com/ZA_k-3-aj-L2wncXttJ5P-b6bPdOKODHL0j_Rh64aFUwfWqZSqPjBF1mA1ePlH1FbFlfgnZ9O6OYH6OBonBrzTHdIFhdL4A2RaDsTjN-loYGsuBAO0m6f_GXDbTd0tRBO9Mn7oR-)
![](https://lh4.googleusercontent.com/FCCWWJjJZBGfHFzOV5lNxRss_RC8np21O1NwQx_CQp84G94uFJunrqN9QxhUz0G2qCOQVMtLxEWwiF2jY6dLTyX-esPQLz_5I4ezrTCT-hGNfBZJqC4ATT_tOcVdEnR0d3jIP582)

## Merging Branches (git merge)
In this case, we have already successfully completed our feature, and are ready to merge with the main branch. Merging is only one way of rejoining two branches, and creates a single commit with two parent commits, the tip of both branches. The other option is rebasing, but we won’t be covering that for now.

To merge, first we will checkout the main branch, and then run the git merge as follows:

```
git checkout main
git merge niceDay
```
![](https://lh3.googleusercontent.com/hR13vskv3I2zkJaNfv0XFX2e8LJKrU8r-hp5Be43qBEHNQAPnxq_IVWaSEKzw7Mw4I6pOPoazSJKZuhlPwlUvTG0LuOdFNeXhS15gNdNTP4Wuv2t_kljd6FCtkTfN_fMPNw14-ak)
From here, we can add, commit, and push to main branch, much like we did with the niceDay branch.
### Merge Conflicts
Something important to note when merging is that __merge conflicts__ can occur, which is when the two branches have both edited the same line. These are resolvable, but may be difficult to work with at first. In our case, since we did not change any lines across the two branches, there was no conflict.

## Stash (git stash)
On occasion, you may want to make changes to another branch, or pull the most recent changes, but are not ready to commit the work you are currently working on. You could copy the files to another folder and move them back later, but a much easier way of doing this is by using the git stash command.

Let’s start by adding a line to our script.py. I added testVar=”test”, but you can add whatever you’d like.
![](https://lh6.googleusercontent.com/qlSAptHFFaeynEM6bQgmIWBKY6HtrDdk9M70IfFE6T1Zu33FmyoN5eGz99kEoS-DNqHvLC5lhEmaVLjJX1xnUD6bKkey5jRDc9JggEWuntu5UWF3ftwDaRkjaOMaX3eNwStuLlae)
Now we run the following commands.
```
git stash script.py
cat script.py
```
![](https://lh6.googleusercontent.com/mLiSn9i4E_990I1zGxUEsM0r3iBawNiQz-c5pjpU_uBuCUpEQTTWICG6u8a_2Axe3dJtHkrgGZbFAVIR8Xm1GjXlNGB7ZMXqP_TNU87GFTb5VNQ8T12bTve_Z5a7imthbOCGNmve)
You’ll notice that our changes have disappeared. We can now do whatever we need to, such as swap branches to work on a separate feature, pull recent changes, and anything else.
Let’s now get the changes back. We’ll run the following commands:
```
git stash pop
cat script.py
```
![](https://lh6.googleusercontent.com/yWK09016t-XAzIljEsx49gP4YbhiyyDQpaxr3VyMo3gjVsEGLADOrQmAv5HhhHHaVBlygE_ntbdiI0ylJzH6U7QEerqWO15NlvCJ6wDHDfYz20H4eMLuy74q_uc9N4JgeoD4Kjf6)
