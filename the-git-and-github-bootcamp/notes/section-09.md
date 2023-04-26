# Git Stashing

Git provides an easy way of stashing these uncommited change so that we can return them later, without having to make unnecessary commits.
`git stash` is a super useful command that helps you save changes that you are not ready to commit. You can stash changes and then come back to them later.
Running `git stash` will take all uncommited changes (staged and unstaged) and stash them, reverting the changes in your working copy.
## Use `git stash pop` to remove the most recently stashed changes in your stash and re-apply them to your working copy.

## Stash Apply
You can use `git stash apply` to apply whatever is stashed way, without removing it from the stash. This can be useful if you want to apply stashed changes to multiple branches.

## Heads Up!
If you have untracked files (files that you have never checked into Git) They will not be included in the stash.
Fortunately, you can use the -u option to tell git stash to include those untracked files.

## Stashing Multiple Times
You can add multiple stashes onto the stack of stashes. They will all be stashed in the order you added them.

## Viewing Stashes
Run `git stash list` to view all stashes

## Applying Specific Stashes
Git assumes that you want to apply the most recent stash when you run `git stash apply`, but you can also specify a particular stash like `git stash apply stash@{2}`

## Dropping Stashes
To delete a particular stash, you can use `git stash drop <stash-id>`

## Clearing The Stash
To clear out all stashes, run `git stash clear`

## Do I really Need This? YES!