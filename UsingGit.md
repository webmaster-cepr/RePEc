# Maintaining RePEc on CEPR's GitHub

## About Git

The best way to describe Git is that it is a version-control system. Say you have a project and you are working with three other people. All your files are stored in one directory and everyone will be making changes to them. You would want to know who is working on which files and what kind of changes they are making, right? This is what Git does.

First you initiate what is called a Git repository in that directory and `commit` all the files to Git. This is your Master branch. You don't want everyone making changes to the Master branch at the same time, though. That would be anarchy!

Each person will clone the repository on their computer and create branches specifically for their work.

Say in our directory we have a file called cats.txt and it lists three cat names: Fluffy, Spots, and Roger. My job is to think of two more cat names. First I create a new branch, using the command `git checkout -b cats`. Then I add the names Yoda and Jarvis to cats.txt. I then commit these changes using the command `git commit -m "Added two cat names to cats.txt`. The `-m` means I'm adding a message to my commit -- "Added two cat names to cats.txt." Done!

But how do the changes get back to the Master branch? This is where GitHub comes in.

## About GitHub

GitHub is a cloud service where anyone can store their repositories. Going back to the example above, say the three people you are working with are all in different cities. GitHub provides a space where everyone can push/pull their changes to the repository. Every repository exists on a url. For example, RePEc
is located at https://github.com/webmaster-cepr/RePEc.git.

After installation and setting up your repository locally, you can push your changes to GitHub. Going back to the cats example, say I'm ready to push my changes to GitHub. I do that with the command `git push origin cats`. Now if you go to the GitHub page and checkout the branches, you'll see `cats`!

Now you're ready to submit a pull request. Pull requests let you tell others about changes you've pushed to a repository on GitHub. Once a pull request is sent, interested parties can review the set of changes, discuss potential modifications, and even push follow-up commits if necessary. If all the changes are accepted, the branch can be merged with the Master branch.

## Learn More

CodeSchool has a fantastic free course on Git [here](https://www.codeschool.com/courses/try-git).

## Installing Git

This [site](https://confluence.atlassian.com/bitbucket/set-up-git-744723531.html) will walk you through the process of installing Git on various operating systems.

## Using Git

### Setting up the Repository Locally

The first time you use git, you'll need to clone the RePEc repository onto your computer.

```git clone https://github.com/webmaster-cepr/RePEc.git```

The version of RePEc that is crawled online is hosted on a GitHub page. That means all your changes need to go into the `gh-pages` branch. You'll need to checkout this branch by creating a version of it locally.

```git checkout -b gh-pages origin/gh-pages```

You can always see which branch you are in by typing `git branch`.

### Fetching Recent Updates

Once the repo is set up locally, you'll want to fetch any recent changes. You should do this every single time you make any changes.

To fetch the most up-to-date changes to any of the branches, use the command:

```git fetch --all``

### Updating the Repo

Once you have fetched all recent changes, you can make changes to the files and push them back to GitHub.

Say you make a change to a file called cats.txt. If you type `git status`, it will tell you that cats.txt has been modified. In order to push the updated cats.txt, you'll first need to `add` the file.

```git add cats.txt```

An easier command to remember, however, is:

```git add -u```

That will add all files that have been updated.

Then commit the changes to Git (not to be confused with GitHub) using the `commit` command. You can add a message that lets others know what you did.

```git commit -m "Updated cats.txt"```

Now you push all changes to GitHub.

```git push origin gh-pages```

You'll also need to fetch the most-recent version of the repository

