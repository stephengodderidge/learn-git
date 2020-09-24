# learn-git-tutorial
A tutorial for those looking to get started using git and github. Originally used on campus at BYU.

Git might not get you a job, but it will certainly be an every day tool. It's how world-class dev orgs ship applications. Let's get started!

> PS - I'll be focusing on GitHub here, but all of the same concepts apply to BitBucket, GitLab, or any other git-based storage site. The UI might look different, but they're all based on the same underlying tech (git).

> PPS - Don't worry, I won't let the git puns git in our way.

The README of this repo is the tutorial, but you'll use the rest of the files to practice forking, committing, open a PR, etc. This won't teach you everything, but I hope it gives you enough of a base if you get stuck in any sticky situations.

## Pre-requisites:
1. You have git installed on your machine
2. You have setup your git config with your email and git username. See the section `Your Identity` in [the First Time Git Setup documentation](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup) if you haven't done this step. You can make sure that you've done this step by running `git config user.name` and `git config user.email`.

## Step 0: Tutorial Overview
In this tutorial, you will be doing the following steps:
1. Fork This Repository
2. Clone Your Newly-Created Fork
3. Create a feature branch on your local repo
4. Add a python script to the `favorite-animals/` folders
5. Commit your changes
6. Push your local feature branch to your remote repo (your fork)
7. Open a Pull Request to the Starting Repository (stephengodderidge/learn-git)


## Step 1: Fork This Repository
Instead of adding your changes directly to someone else's repo, you can create a copy of their repository to work with. When you create this copy, we call it "forking the repository."

Conceptually, think about hitting a fork in the road -- the road splits into two. This is the same with forking in git. Forking simply creates a snapshot of the base repository (`stephengodderidge/learn-git`) that you can make changes to. Once you make changes, you can open a pull request (PR) from a feature branch on your fork to the base repo's master. More on this later.

After you fork your repo, your newly-created repo will be referred to as a "fork." This might sound weird, but just go with it. I promise it will stick eventually.

1. Make sure you're on the base page of the `learn-git` repository: [https://github.comstephengodderidge/learn-git](https://github.com/stephengodderidge/learn-git).
2. In the top right-hand corner, you'll see a button that says "Fork". Click it.
    You'll see a screen that shows "Forking repository". You'll now find yourself on a new repo page. If you look in the top left, you'll see that this repo is based on your `<your-github-username/learn-git>`.

Congrats! You've created a fork! This is simply a copy of the base repository `stephengodderidge/learn-git`

## Step 2: Clone Your Newly-Created Fork
You'll need to clone your fork repository to your local environment. "Clone" might just sound like a fancy way to say "download", but cloning keeps the connection between the remote repository (in GitHub) so you can add our changes (commits) back to the remote. By the end of this step, your will have cloned the repository into a folder on your computer.

1. Go to your fork and hit the green "Code" button. Select HTTPS.
> There are several ways to clone the repository, including SSH and GitHub's own command-line interface. We're going to keep it simple and go with HTTPS.
2. Copy the link in the box. This link is the url to the repository. It should look something like https://github.com/your-username-here/learn-git.git
3. If you're on a Mac, open your terminal. If you're on windows, use Git BASH. I'm not a PC user, but I'm fairly certain you can download Git BASH on [gitforwindows.org](https://gitforwindows.org/)
4. Navigate to the parent directory you'd like to download it to.
5. Type the following command: `git clone <insert-the-https-url-here>`

And Voila! You've officially cloned the repository onto your local machine. Navigate to your repository by running a quick `cd learn-git`

### Step 2.5: Adding a "Remote" back to the original repository
One of the trickiest parts of Git is updating your local branch with the changes in the remote repository (`stephengodderidge/learn-git` in our case). In order to do this, we'll need to add a "remote" reference to our local git branch.

1. Run `git remote -v` to see all of your current remotes. You should see one: `origin` and that should reference your forked remote repo. Don't worry about the difference between `(fetch)` and `(push)` for now.
2. Next, add a remote called `upstream` with the URL of the original repository by running `git remote add upstream https://github.com/stephengodderidge/learn-git.git`.
3. Run `git remote -v` to see that new remote added

Congrats! You added your new remote! Now, when updates are added to that repository, we'll be able to _pull_ those changes to your local repository. We'll practice this after we open our pull request in the Bonus section of this tutorial.


## Step 3: Create a feature branch on your local repo
Now that you're on your local repository, you can focus on making our changes. Your assignment is to add a script to the `favorite-animals/` directory. Yes, very complicated. It's basic, but the goal is to learn git. You'll name your script `your_firstname_and_lastname.py`, commit it to your local repo, push your changes to your fork, and open a repo. Phew, that's a lot! Don't worry, you'll focus on creating the feature branch in this step.

1. Make sure you're in the root of your local repo. Use `cd` to get there. To make sure you're on the master branch, run `git status`. The output will show you your current branch. If you're not on your default branch, run the command in step three to switch back. We'll come back to `git status` in a minute.

2. Run `git branch my-animal`. This creates a snapshot (a branch) of your current branch (`master` in this case) named `my-animal`. You could have named this branch whatever you'd like (ex: `git branch covid-sucks`). In this case, you'll be adding our simple script to this branch.

3. Now that you have our new branch created, you need to switch our current branch to the new branch. You refer to this process of branch switching as "checking out a branch." Run `git checkout my-animal`. Now, run `git status` to confirm that the current branch as `my-animal`.

4. BONUS - in the future, when you create branches, you can use `git checkout -b <insert-branch-name>` as a shortcut to `git branch` and `git checkout`. This is the same thing as running `git branch my-animal && git checkout my-anmial`. Personally, I _always_ use `git checkout -b`.

And voila! You've created your feature branch. You're all set to make these changes.

## Step 4: Add a Python script
In this step, you're going to add a script. The important part is that you're going to make changes locally, commit those changes to our feature branch, and ultimately you'll be pushing these changes to our fork.

1. Open the `learn-git` folder in your code editor.
2. Add a new file to the `favorite-animals/` folder.
3. Name this file `<your-first_name_and_last_name>.py`. Example: stephen_godderidge.py
4. Add a print statement to the file. This could be anything you want. If you'd like to play along, add a statement that describes your favorite animal. My script does the following:
```python
print("My favorite animals are sloths")
```
5. Save your new file.

Now you're ready to move on and actually commit your changes!

## Step 5: Commit your changes
Committing your changes adds your changes to the current branch. Before you commit your changes, you have to _stage_ your changes. This step may seem trivial when you're working on a few files (especially in our case), but this step becomes more helpful as you work on more files at once.

> Think of an assembly line that creates new cars. The cars are assembled, and they go to a separate location for a quality check before shipping out to the customer. This is what your staged changes are. You work on a bunch of changes locally, and then stage the changes (quality check) before they're finally committed (shipped to the customer). Once you've staged your changes, you can review your changes before finally committing them.

Think of committing your staged changes as saving your changes to your repository. Follow the steps below, and we'll come back to this question.

1. Make sure you saved your new script.

2. Run `git status` to see the files that have been changed. You should see a `Changes not staged for commit:` section. Underneath, you should see the file path to your new script (example: `favorite-animals/stephen_godderidge.py`). These are changes that you have saved to your files, but they aren't currently setup to be committed yet. _Your changes aren't staged yet_. In fact, you'll need _add_ them to the staged files before you can commit them.

3. Run `git add favorite-animals/<insert_your_script_name>.py`. This step adds the file to the files staged for the commit.

    > Note -- if you'd like to stage all of the files you've made changes to locally, you can simply run the shortcut `git add .` instead of adding each file individually.

4. Run `git status` again to confirm the changes have been added to the staged files. You should see a `Changes to be committed:` section. Underneath, you should see the new file path. This means your files are ready to be committed.

5. Run `git commit -m "add my new script"`. This commits the changes, and allows us to add a git commit message at the same time. Now, our branch has been updated to point to this new commit.

6. Run `git status` to check that the files have been added. You should see a message that says `nothing to commit, working tree clean`

And voila! You've committed your changes.

Now, back to the question – _How is saving your files on your computer different from committing your changes to your repository?_ Committing your changes bundles all of your changes into a single commit and adds that commit to your branch. Once your branch includes this new commit, you are able to push your changes up to your remote repository. From there, someone else could pull your changes, create a branch from your branch, and start adding new commits. By stringing these commits together, the repository has an accurate view of the current state of the branch.

Once you have several commits on a branch, you can choose to do a whole host of different actions - undo (wipe away the changes completely), unstage (un-commit the changes, and add them to the unstaged files on your local workspace), and more.

## Step 6: Push your local feature branch to your remote repo (your fork)
Now that you have your changes committed, you need to _push_ those changes to your remote repository, which is a fork of the original `learn-git` repository. At the end of this step, your remote repository will include your feature branch.

1. Check which branch you're on by running `git status`. If you're not on your feature branch, go ahead and checkout that branch.
2. Run `git push`. Git should automatically display a message similar to:
    ```
    The current branch my-animal has no upstream branch.
    To push the current branch and set the remote as upstream, use

        git push --set-upstream origin my-animal

    ```
    Don't worry, nothing is wrong. Git is simply helping us with your next step. Git is telling you that you need to set the upstream branch of your local branch to the remote copy (origin). Phew, that was a lot. Let's break it down.

     So, what is `origin`? This is the term that git uses to refer to a remote repo. In our case, origin is our remote repository (our fork). The upstream branch is the branch tracked on the remote repository by your local branch. So, in our case, we're setting up our local `my-animal` branch to track any changes that happen in our origin's (our fork's) `my-animal` branch. When would this be useful? Well, say we have multiple developers making changes to a feature branch. We need a way to pull down the latest commits

     [More on that in this helpful article](https://devconnected.com/how-to-set-upstream-branch-on-git/#:~:text=Upstream%20branches%20define%20the%20branch,set%20upstream%20branches%20on%20Git.)
3. Do as git suggests and run `git push --set-upstream origin my-animal`. You'll see a bunch of update statements like `resolving deltas` and `Writing objects:`. This means git is pushing your local branch to your remote repo. You'll also see a helpful line that should read:

```
remote: Create a pull request for 'my-animal' on GitHub by visiting:
remote:      https://github.com/<insert-your-github-username>/learn-git/pull/new/my-animal
```

Copy this URL. You're going to need it in a minute!

4. Bonus -- go to your fork in your browser. In the top left corner, you should see a button that says `Master`. Click it, and see that your branch is there. You can open you branch and navigate to your script. You should be able to see your changes. Pretty cool right?

## Step 7: Open a Pull Request to the Starting Repository (stephengodderidge/learn-git)
Our next goal is to add our commits to the master branch of the real `learn-git` repo so others can see our script and make changes if they'd like. In order to do this, you need to submit a request to pull those changes into the repo. In other words, you need to open a __pull request__.

This Pull Request needs to be approved by the owners of the repository before it can be _merged_ into master. Different companies have different approval processes (example: multiple reviewers from different teams), but our use case is simple. You're simply focused on opening the pull request.

1. Open a request by going to the link in the last step of Step 6. It should look like `https://github.com/<insert-your-github-username>/learn-git/pull/new/my-animal`. This should take you to a page with the title of __Open a pull request__.
2. Name your Pull Request whatever you want. Add some comments if you'd like.
3. Once you've added your PR name and comments, go ahead and click the `Create Pull Request`.

Congrats! You've opened your first pull request!! Go ahead and take a look around at the different tabs. See if you can find where you can view your changes (Hint: look for files). You can also view your commit(s).

Because you don't own the upstream repo (`stephengodderidge/learn-git`), you won't be able to approve your own PR. I'll keep an eye on this repo, and once I see your PR, I'll approve it and merge it into master.

Note that if I wanted to, I could add collaborators that contribute directly to this repository by going to Settings -> Manage Access -> Invite a Collaborators. This would be particularly useful for group projects.


# And We've finished the Tutorial! Pat yourself on the back, you're well on your way to mastering git

## More Content:

### Commands that were used in this tutorial:
```
git clone <insert-the-https-url-here>
git remote -v
git remote add <insert-the-remote-name> <insert url to the original repository>
git status
git branch <insert-name-of-branch>
git checkout <insert-name-of-branch>
git checkout -b <insert-name-of-branch>
git add <insert-name-of-file>
git add .
git commit -m "<insert-a-message-to-describe-the-commit>"
git push
git push --set-upstream origin <insert-name-of-current-local-branch>
```

> note: DON'T Simply run these commands in order. There is some overlap. This list is mainly meant to be a reference for later. Remembering all of the git commands can be tricky. __I still regularly google Git commands__, and I've used Git every day for the last 3 years or so.


### Other Great Tutorials:
Need more practice? Take a look at some of these tutorials to expand your experience (Don't worry, they're free!):
* [Kent C Dodd's Intro to GitHub](https://egghead.io/lessons/javascript-introduction-to-github) -- an Awesome course that helped me fill in some gaps of my knowledge about GitHub way back when.
* [Kent C Dodd's Intro to Contributing to Open Source](https://egghead.io/courses/how-to-contribute-to-an-open-source-project-on-github) -- the best way to learn is to do, and this is a great course for contributing to real projects on github.
* Another good [step-by-step guide from opensource.com](https://opensource.com/article/18/1/step-step-guide-git)
* Here's [an interactive git playground](https://learngitbranching.js.org/?NODEMO) that you can practice branching


### Topics Not Covered
This tutorial doesn't cover these topics, but they're still useful to know after you've learned everything included above:

* __How to undo your last commit__ - See the second answer to [this post on Stackoverflow](https://stackoverflow.com/questions/927358/how-do-i-undo-the-most-recent-local-commits-in-git).

* __How to view your current changes in VSCode__ - I definitely recommend using VSCode if you can. I run all of my git commands and logic through the command line, but I use the git tab on the far right toolbar to view the changes to my files. See `[the VS Code documentation for more info](https://code.visualstudio.com/docs/editor/versioncontrol).

* __How to _Rebase_ Your Feature Branch Onto the latest version of Master__ - Let's say you're working on your feature branch for a few days, and the upstream master has been updated, and you need the new changes on your feature branch. The process to do this is called "rebasing". It's a good one to know. I'll work on adding a tutorial for it, but in the meantime, you can always Google "how to rebase my branch onto master" and a Stack Overflow link should pop up.

* __How to Resolve Merge Conflicts__ - Let's say you open a PR that changes files that someone else changed _after you created your branch_. Your branch doesn't have these changes, so Git isn't sure how it should treat the order of the commits. This is called a Merge Conflict.
    This is the trickiest part of working in git. This will most certainly cause you headaches in the future. It's worth an entire tutorial by itself. I'm working on adding a full-fledge tutorial, but here are the basic steps: (A) Pull the latest changes from the upstream master into the local master. (B) Checkout the feature branch that has the conflicts. (C) Rebase your feature branch onto master. (D) Use the interactive rebasing process to resolve any conflicts. (E) Force push your changes. Again, I'll add a full-fledge tutorial soon, but hopefully these steps give you a guide for things to Google.

### Terms to be familiar with:
Here are some of the terms we've used in the tutorial. This isn't meant to be a comprehensive git dictionary, but hopefully it helps fill in any gaps you might have after the tutorial.

* __repository__ - the git-enabled folder. Think of it as your project folder with a hidden .git folder inside. This repository can have branches, forks, and various commits. The main goal is that it tracks all of the versions of a project, both working and development. AKA "a repo."

* __branch__ - think of branches as pointers to a snapshot of your changes. The default branch in git is referred to as `master` or `main`. Branches are used for new feature development. The process to switch to a new branch is called "check out a branch." Each time you create a branch, you create a new snapshot of the branch you currently had checked out.

* __commit__ -
  * _verb_: to write your changes to whichever branch you're currently on.
  * _noun_: refers to the new changes themselves. Once you've committed your changes, you can undo those changes by undoing the commit. Git uses hashes to refer to your various commits.

* __remote__ - opposite of local. Used to describe a repo that exists in GitHub (or a different git service). By default, your local repo will have one remote: `origin`. You can add other remotes as well. This is helpful when you want to pull the latest changes from the original repository that your fork is generated from (see Step 2.5 above in the tutorial).

* __local__ - opposite of remote. Used to describe a repo that exists on your local machine.

* __fork__ - a copy of someone else's repository. This new copy is owned by your GitHub user, so you're able to make changes to it. This is a very common approach in the open-source contributing world. See Step 1.

* __pull request__ - a request to merge your changes into a branch (usually master). Think of it as a request to _pull your feature branch's changes into the master branch_. Note that these feature branches can be on a fork of the original/upstream/main repo.

* __push__ - Used to describe the process of adding your commit to another branch, usually from a local to a remote. Example: _Push your changes (commit) to your remote repo_.

* __pull__ - Used to describe the process of adding the changes from one branch to another, usually from a remote to a local. _Pull in the latest changes from the master branch_.

*__master__ - Used as the default branch for any repository. There is nothing special about this branch; it's simply the one that is designated as the main branch

    > Because of today's society's realization of systemic racism, there are movements to rename "master" to "main." I think this is an important and necessary shift in our verbiage as developers. GitHub will soon make it the default for all repositories. However, in the meantime, for those learning git, it is still helpful to learn "master" as the default branch. New developers will most certainly come across repos with a `Master` branch and need to be aware of what that means. For this reason, I'm going to continue to use `master/main` to refer to the default branch.

__Did I miss a term? Go ahead and open a PR to add any you think should be added!__
