# Rebasing
When I first learned Git, I was told to avoid rebasing at all costs.
"It can really fuck thigs up"
"It's not for beginners!"
So I avoided the `git rebase` command for years!
It is actually very useful, as long as you known when NOT to use it!
There are two main ways to use the `git rebase` command:
- as an alternative to merging
- as a cleanup tool

The feature branch has a bunch of merge commits. If the master branch is very active, my feature branch's history is muddies
## Rebasing!
We can instead rebase the feature branch onto the master branch. This moves the entire feature branch so that it BEGINS at the tip of the master branch. All of the work is still there, but we have re-written history.
Instead of using a merge commit, rebasing rewrites history by creating new commits for each of the original feature branch commits
WE can also wait until we are done with a feature and then rebase the feature branch onto the master branch

## Why Rebase?
We get a much cleaner project history. No unnecessary merge commits! we end up with a linear project history.

## WARNING!
Never rebase commits that have been shared with others. If you have already pushed commits up to Github DO NOT REBASE THEM unless you are positive no on the team is using those commits.
## SERIOUSLY!
You do not want to rewrite any git history tat other people already have. It is a pain to reconcile the alternate histories!
## Rebasing
There are two main ways to use the `git rebase` command:
- as an alternative to merging
- as a cleanup tool

## Rewriting History
Sometimes we want to rewrite, delete, rename, or ever reorder commits (before sharing them) We can do this using git rebase!

## Interactive Rebase
Running `git rebase` with the `-i` option will enter the interactive mode, which allows us to edit commits, add files, drop commits, etc. Note that we need to specify how we want to rewrite commits.
Also, notice that we are not rebasing onto another branch. Instead, we are rebasing a series of commits onto the HEAD they currently are based on.

## What Now?
In our text editor, we will see a list of commits alongside a list of commands that we can choose from. Here are a couple of the more commonly used commands:
- pick - use the commit
- reword - use the commit, but edit the commit message
- edit - use commit but stop for amending
- fixup - use commit contents but meld it into previous commit and discard the commit message
- drop - remove commit