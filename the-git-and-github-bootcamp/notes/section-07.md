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


