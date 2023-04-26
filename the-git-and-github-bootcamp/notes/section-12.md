# Fetching & Pulling

## A Closer Look At Cloning
* - * - (master) => `git clone` => * - * - (origin/master)
My computer is working with a clone of the origin/master. It is a reference.
This is a "remote tracking branch". It is a reference to the state of the master branch on the remote. I cannot move this myself. It is like a bookmark pointing to the last known commit on the master branch on origin.

## Remote Tracking Branches
"At the time you last communicated with this remote repository, here is where x branch was pointing"
They follow this pattern <remote>/<branch>. 
- origin/master references the state of the master branch onthe remote repo named origin.
- upstream/logoRedisn references the state of the logoRedesign branch on the remote named upstream (a common remote name)

## Remote Branches
Run `git branch -r` to view the remote branches our local repository know about.
Once you have cloned a repository, we have all the data and Git history for the project at that moment in time. However, that does not mean it is all in my workspace!
The github repo has a branch called puppies, but when I run git branch I do not see it on my machine! All I see is the master branch. What is going on?

## I Want to work on the puppies brannch locally!
I could `checkout origin/puppies`, but that puts me in detached HEAD.
I want my own local branch called `puppies`, and I want it to be connected to `origin/puppies`, just like my local `master` branch is connected to `origin/master`

## It is Super Easy!
Run `git switch <remote-branch-name>` to create a new local branch from the reomte branch of the same name
`git switch puppies` make me a local puppies branch AND sets it up to track the remote branch origin/puppies.
### Note
The new command `git switch` makes this super easy to do! It used to be slightly more complicated using git checkout
`git checkout -track origin/puppies` 

## Fetching
Fetching allows us to download changes froma remote repository, BUT those changes will not be automatically integrated into our working files. It lets you see what others have been working on, without having to merge those ghanges into your local repo.
Think of it as "please go and get the latest information from Github, but don't screw up my working directory."

## Git Fetch
The `git fetch <remote>` command fetches branches and history from a specific remote repository. It only updates remote tracking branches.
`git fetch origin` would fetch all changes from the origin remote repository
`git fetch` by default will fetch origin
We can also fetch a specific branch from a remote using `git fetch <remote> <branch>
For example, `git fetch origin master` would retrieve the latest information from the master branch on the origin remote repository.

## Pulling
`git pull` is another command we can use to retrieve changes from a remote repository. Unline fetch, pull actually updates our HEAD branch with whatever changes are retrieved from the remote.
"go and download data from Github AND immediately update my local repo with those changes"
`git pull` = `git fetch` + `git merge`
To pull, we specify the particular remote and branch we want to pull using `git pull <remote> <branch>`. Just like with git merge, it matters WHERE we run this command from. Whaever branch we run it from is where the changes will be merged into.
`git pull origin master` would fetch the latest information from the origin's master branch and merge those changes into our current branch.
### Pull can result in merge conflict!

## An even easier syntax!
If we run `git pull` without specifiying a particular remote or branch to pull from, git assumes the following:
- remote will default to origin
- branch will default to whatever tracking connection is configured for your current branch
Note: This behavior cane be configured, and tracking connections can be changed manually. Most people do not mess with this though.

## git fetch vs git pull
`git fetch` | `git pull`
-|-
 Gets changes from remote branch(es) | Gets changes from remote branch(es)
 Updates the remote-tracking branches with the new changes | Updates the current branch with the new changes, merging them in
 Does not merge changes onto your current HEAD branch | Can result in merge conflicts
 Safe to do at any time | Not recommended  if you have uncommited changes!

#