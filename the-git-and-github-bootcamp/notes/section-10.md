# Undoing Stuff and Time Travelling

## Checkout
The `git checkout` command is like a Git Swiss Army knife. Many developers think that it is overlaoded, which is what lead to the addition of the git switch and git restore commands.
We can use checkout to create branches, switch to new branches, restore files, and undo history!
we can use `git checkout commit <commit-hash>` to view a previous commit.
Remember, you can use the `git log` command to view commit hashes. We just need the first 7 digits of a commit hash.
Don't panic when you see the following message...
`git checkout d8194d6`

## Detached HEAD ??
Don't panic when this happens! It is not a bad thing!

You have a couple options:
1. Stay in detachd HAED to examine the contents of the old commit. Poke around, view files, etc.
2. Leave and go back to wherever you were before - reattach the HEAD
3. Create a new branch and switch to it. You can now make and save changes since HEAD is no longer detached.
- If you checkout an old commit and decide you want to return to where you were before just switch back to the branch you would like to be on.

## Another Option
Here is another shorter option to revert a file...
Rather than typing HEAD, we can substiture `--` followed by the file(s) we want to restore. `git checkout -- <file>`

## Restore
`git restore` is a brand new Git command that helps with undoing operations.
Because it is so new, most of the existing Git tutorials and books do not even mention it, but it is worth knowing about!
Recall that `git checkout` does a million different things, which many git users find very confusing. `git restore` was introduced alongside with `git switch` as alternatives to some of the uses for `checkout`.

## Unmodifying Files With Restore
Suppose that you have made some changes to a file since your last commit. You have saved the file, but then realize that you definitly do NOT want those changes anymore.
To restore the file to the contents in the HEAD, use `git restore <file-name>`
NOTE: The above command is not "undoable". If you have uncommited changes in the file, they will be lost!
`git restore <file-name>` restores using HEAD as the default source, but we can change that using the `--source` options.
For example, `git restore --source HEAD~1 home.html` would restore the contents of `home.html` to its state from the commit prior to `HEAD`. You can also use a particular commit hash as the source.

## Unstaging Files with Restore
If you have accidentally added a file to your staging area with `git add` and do not wish to include it in the next commit, then you can use `git restore` to remove it from staging.
Use the `--staged` option like this:
`git restore --staged app.js`

## Feeling Confused?
`git status` reminds you what to use!

## Git Reset
Suppose you have just made a couple of commits on the master branch, but you actually meant to make them on a separate branch instead. To undo those commits, you could use `git reset`
`git reset <commit-hash>` will reset the repo back to a specific commit. The commits are gone!

# Reset --hard
If you want to undo both the commits AND the actual changes in your files, you can use the `--hard` options.
For example `git reset --hard HEAD~1` will delete the last commit and associated changes.

# Git Revert
Anothre similar sounding yet confusing command that has to do with undoing changes.
`git revert` is similar to `git reset` in that they both 'undo' changes, but they accomplish it in different ways.
`git reset` actually moves the branch pointer backwards, eliminiting commits.
`git revert` instead creates a new brant new commit, which reverses/undos the changes froma commit. Because it results in a new commit, you will be prompted to enter a commit message.

## Which One To Use?
Both `git reset` and `git revert` help reverse changes, but there is a significant diference when it comes to collaboration (which we have yet to discuss)
If you want to reverse some commits that other people already have on their machines, you should use revert.
If you want to reverse commits that you have not shared with others, use reset and no one will ever know!

