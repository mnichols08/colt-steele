# Merging Branches

## Merging
Branching makes it super easy to work within self-contained contexts,b ut often we want to incorporate changes from one branch into anogher!
We can do this using the git merge command
The merge command can sometimes confuse students early on. Remember these two merging concepts:
- We merge branches, not specific commits
- We always merge to the current HEAD branch

## Merging Made Easy
To merge, follow these basic steps:
1. Switch to or checkout the branch you want to merge the change into (the receiving branch)
2. User the git merge command to merge changes from a specific branch into the current branch.

## Heads Up!
Depending on the specific changes you are trying to merge, Git may not be able to automatically merge. This results in merge conflicts, which you need to manually resolve.

## What The...
When you encounter a merge conflict, Git warns you in the console that it could not automatically merge.
It also changes the contents of your files to indicate that conflicts that it wants you to resolve.
The content from your current HEAD (the branch you are trying to merge content into) is displayed between the <<<<<HEAD and ======
The content from the branch you are trying to merge from is dislayed between the ====== and >>>>>> symbols.

## Resolving Conflicts
Whenever you encounter merge conflicts, follow these steps to resolve them:
1. Open up the file(s) with merge conflicts.
2. Edit the file(s) to remove the conflicts. Decide which branch's content you want to keep in each conflict. Or keep the content from both.
3. Remove the conflict "markers" in the document.
4. Add your changes and then make a commit!

## Deleting a Branch
`git branch -d <branch-name>`

### Git Merging Exercise

This exercise is a little bit different.  Rather than following my exact instructions step by step, I'd like for you to come up with your own scenarios that meet my requirements.

Start by creating a new repo.  Make a file or two in the repo for you to work on.

If you need some inspiration...I'll be working in a file called `greetings.txt` It will contain greetings in different languages.

## Part 1: Fast Forward Merge

**Your goal is to generate a fast forward merge. Demonstrate that you understand how FF merges work by creating one on your own!**

Make a new branch. Do some work in the repo such that when you merge the new branch into master, it results in a fast forward merge.  Merge that branch into master and see if you were right!

## Part 2: Merge Commit (No Conflicts)

Your goal is to generate a merge commit with NO MERGE CONFLICTS.

Create a new branch. Make some changes to the repo such that when you merge the new branch into master, it results in a merge commit.  The merge should not result in any conflicts. Merge that branch into master and see if you were right!

## Part 3: Conflicts!

Your goal is to generate merge a conflict!

Create a new branch.  Make some changes to the repo such that when you merge the new branch into the master branch, it results in a merge conflict. Merge that branch into master and see if you were right! Resolve the conflict!
