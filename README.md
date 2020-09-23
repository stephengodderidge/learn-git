# learn-git-tutorial
A tutorial for those looking to get started using git and github. Git might not get you a job, but it will certainly be an everday tool. It's how world-class dev orgs ship your applications. Let's get started!

> PS - I'll be focusing on GitHub here, but all of the same concepts apply to BitBucket, GitLab, or any other git-based storage site. The UI might look different, but they're all based on the same underlying tech (git).

> PPS - Don't worry, I won't let the git puns git in our way.

The README of this repo is the tutorial, but we'll use the rest of the files to practice forking, commiting, open a PR, etc. This won't teach you everything, but I hope it gives you enough of a base if you get stuck in any sticky situations.


## Step 0: Tutorial Overview
In this tutorial, we will be doing the following steps:
1. Fork this repo
2. Clone the forked repo
3. Create a feature branch on your local repo
4. Add a python script to the `favorite-animals/` folders
5. Commit your script to your local feature branch
6. Push the local feature branch to your remote repo
7. Open a PR from your remote repo back to this repo

For bonus steps, we'll do the following:
7. Pull in the latest changes from this repo (not your fork) into your local repo
8. Resolve Merge Conflicts

We won't cover these topics, but they're still useful to know after you've learned everything else:
* How to undo your last commit. See the second answer to [this post on Stackoverflow](https://stackoverflow.com/questions/927358/how-do-i-undo-the-most-recent-local-commits-in-git).
* How to view your current changes in VSCode. I definitely recommend using VSCode if you can. I run all of my git commands and logic through the command line, but I use the git tab on the far right toolbar to view the changes to my files. See `[the VS Code documentation for more info](https://code.visualstudio.com/docs/editor/versioncontrol).


## Step 1: Fork This Repository
Instead of adding your changes directly to someone else's repo, we can create a copy of their repository to work with. When we create this copy, we call it "forking the repository."

Conceptually, think about hitting a fork in the road -- the road splits into two. This is the same with forking in git. Forking simply creates a snapshot of the original repository that you can make changes to. Once you make changes, you can open a PR from a feature branch on your fork to the original repo's master. More on this later.

After you fork your repository, your newly-created repo will be referred to as a "fork." This might sound weird, but just go with it. I promise it will stick eventually.

## Step 2: Clone Your Newly-Created Fork
We'll need to clone your fork repository to our local environment. "Clone" might just sound like a fancy way to say "download", but cloning keeps the connection between the remote repository (in GitHub) so we can add our changes (commits) back to the remote. By the end of this step, we will have cloned the repository into a folder on your computer.

1. Go to your fork and hit the green "Code" button. Select HTTPS.
> There are several ways to clone the repository, including SSH and GitHubs own command-line interface. We're going to keep it simple and go with HTTPS.
2. Copy the link in the box. This link is the url to the repository. It should look something like https://github.com/your-username-here/learn-git.git
3. If you're on a Mac, open your terminal. If you're on windows, use Git BASH. I'm not a PC user, but I'm fairly certain you can download Git BASH on [gitforwindows.org](https://gitforwindows.org/)
4. Navigate to the parent directory you'd like to download it to.
5. Type the following command: `git clone <insert-the-https-url-here>`

And Voila! You've officially cloned the repository onto your local machine. Navigate to your repository by running a quick `cd learn-git`


## Step 3: Create a feature branch on your local repo
Now that you're on your local repository, we can focus on making our changes. Your assignment is to add a script to the `favorite-animals/` directory. Yes, very complicated. It's basic, but the goal is to learn git. We'll name your script `your_firstname_and_lastname.py`, commit it to your local repo, push your changes to your fork, and open a repo. Phew, that's a lot! Don't worry, we'll focus on creating the feature branch in this step.

1. Make sure you're in the root of your local repo. Use `cd` to get there. To make sure we're on the master branch, run `git status`. The output will show you your current branch. If you're not on your default branch, run the command in step three to switch back We'll come back to `git status` in a minute.

2. Run `git branch my-animal`. This creates a snapshot (a branch) of your current branch (`master` in this case) named `my-animal`. We could have named this branch whatever you'd like (ex: `git branch covid-sucks`). In this case, we'll be adding our simple script to this branch.

3. Now that we have our branch created, we need to switch our current branch to that. We refer to this process of branch switching as "checking out a branch." Run `git checkout my-animal`.

4. BONUS - in the future, when you create branches, you can use `git checkout -b <insert-branch-name>` as a shortcut to `git branch` and `git checkout`. This is the same thing as running `git branch my-animal && git checkout my-anmial`. Personally, I _always_ use `git checkout -b`.

And voila! You've created your feature branch. We're all set to make these changes.

## Step 4: Add your script.
In this step, we're going to add a script. The important part is that we're going to make changes locally, commit those changes to our feature branch, and ultimately we'll be pushing these changes to our fork.

1. Open the `learn-git` folder in your code editor.
2. Add a new file to the `favorite-animals/` folder.
3. Name this file `<your-first_name_and_last_name>.py`. Example: stephen_godderidge.py
4. Add a print statement to the file. This could be anything you want. If you'd like to play along, add a statement that describes your favorite animal. My script does the following:
```python
print("My favorite animals are sloths")
```
5. Save your new file.

Now we're ready to move on and actually commit our changes!

## Step 5: Commit your changes
Committing your changes adds your changes to the current branch. Think of it as saving your changes to your repository. How is committing your changes different from saving the files you changed? Good question. Go through this step, and we'll come back to that.

1. Make sure you saved your new script.
2. Run `git status` to see the files that have been changed. You should see a `Changes not staged for commit:` section. Underneath, you should see the file path to your new script (example: `favorite-animals/stephen_godderidge.py`). These are changes that you have saved to your files, but they aren't currently setup to be committed yet. In fact, we'll need _add_ them to the staged files before we can commit them.
3. Run `git add favorite-animals/<insert_your_script_name>.py`. This step adds the file to the files staged for the commit.
4. Run `git status` again to confirm the changes have been added to the staged files. You should see a `Changes to be committed:` section. Underneath, you should see the new file path. This means your files are ready to be committed.
5. Run `git commit -m "add my new script"`. This commits the changes, and allows us to add a git commit message at the same time. Now, our branch has been updated to point to this new commit.
6. Run `git status` to check that the files have been added. You should see a message that says





In this tutorial, we will be doing the following steps:
1. Fork this repo
2. Clone the forked repo
3. Create a feature branch on your local repo
4. Add a python script to the `favorite-animals/` folders
5. Push the local feature branch to your remote repo
6. Open a PR from your remote repo back to this repo




## Next

#### Commands that were used:
`git clone <insert-the-https-url-here>`
`cd <insert-repo-name-here>`


## Other common commands:
git log -- shows the log of commits to your repo. Shows the hashes of the commits, along with their commit messages


#### Terms to be familiar with:
Here are some of the terms we've used in the tutorial. This isn't meant to be a comprehensive git dictionary, but hopefully it helps fill in any gaps you might have after the tutorial.

* __repository__ - the git-enabled folder. Think of it as your project folder with a hidden .git folder inside. This repository can have branches, forks, and various commits. The main goal is that it tracks all of the versions of a project, both working and development. AKA "a repo."

* __branch__ - think of branches as pointers to a snapshot of your changes. The default branch in git is referred to as `master` or `main`. Branches are used for new feature development. The process to switch to a new branch is called "check out a branch." Each time you create a branch, you create a new snapshot of the branch you currently had checked out.

* __commit__ -
  * verb: to write your changes to whichever branch you're currently on.
  * noun: refers to the new changes themselves. Once you've committed your changes, you can undo those changes by undoing the commit. Git uses hashes to refer to your various commits.

* __remote__ - opposite of local. Used to describe a repo that exists in GitHub (or a different git service)

* __local__ - opposite of remote. Used to describe a repo that exists on your local machine.

* __fork__ - a copy of someone else's repository that exists under your user. This is a very common approach in the open-source contributing world. See Step 1.

* __pull request__ - a request to merge your changes into a branch (usually master). Think of it as a request to _pull your feature branch's changes into the master branch_. Note that these feature branches can be on a fork of the main repo.

* __push__ - Used to describe the process of adding your commit to another branch, usually from a local to a remote. Example: _Push your changes (commit) to your remote repo_.

* __pull__ - Used to desribe the process of adding the changes from one branch to another, usually from a remote to a local. _Pull in the latest changes from the master branch_.

*__master__ - Used as the default branch for any repository. There is nothing special about this branch; it's simply the one that is designated as the main branch

> Because of today's society's realization of systemic racism, there are movements to rename "master" to "main." I think this is an important and necessary shift in our verbiage as developers. GitHub will soon make it the default for all repositories. However, in the meantime, for those learning git, it is still helpful to learn "master" as the default branch. New developers will most certainly come across repos with a `Master` branch and need to be aware of what that means. For this reason, I'm going to continue to use `master/main` to refer to the default branch.


__Did I miss a term? Go ahead and open a PR to add any you think should be added!__
