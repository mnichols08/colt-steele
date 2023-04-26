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
If you want to reverse commits that you have not shared with others, use reset and no one will ever know!#

## Undoing Things Exercise

This exercise is based around the Beatles' song Yesterday, and the evolution of its lyrics over time. 

- Clone the repo I've created for you, using the following command (make sure you're not already in a repo when you run it!) [x] - modified

```
git submodule add https://github.com/Colt/yesterday-exercise /Exercises/yesterday-exercise
```

- Change into the newly created directory.  You should see a file called `lyrics.txt`
- Take a look at the commit history.  You should see 8 commits on the master branch.
- Go "back in time" by checking out the very first commit.  Remember, this puts you in detached HEAD.  Take a look at the `lyrics.txt` file to verify things have changed.  Then, leave detached HEAD by returning to the master branch.
- Go back to the commit where the original version of the lyrics was completed.  The commit has the message "finish original lyrics".  Create a new branch called `scrambled-eggs` based upon this commit.
- Go back to the `master` branch
- Delete everything in the `lyrics.txt` file.  Save the file.
- Oh no, that was a mistake!  USING A GIT COMMAND, discard the changes you made to `lyrics.txt` since the last commit. We saw a couple of ways of achieving this.
- Suddenly you get a creative itch! You want to write your own parody lyrics!  Replace the contents of `lyrics.txt` with the following lyrics (from [this website](http://www.amiright.com/parody/60s/thebeatles1981.shtml))
    
    ```
    404
    Guess this ain't the page you're looking for
    On this website there are thousands more
    With no error 404
    
    Suddenly
    This is not the page you thought you'd see
    But it's not an error 403
    Yes, 404s come easily
    ```
    
- Add and commit the changes on the `master` branch
- Add this to the bottom of the `lyrics.txt` file:
    
    ```
    Why it has to show, I don't know
    Or what it's for
    You typed something wrong?
    Here's no song - it's 404
    
    404
    Adding 1% to twenty score
    (I put that line in 'cause it scans, no more)
    "Goodbye" from error 404
    ```
    
- Add and commit the changes to the `master` branch
- After more consideration, you realize that you actually don't want the previous two commits (the 404 parody lyrics) on the master branch.  You want to move them to a new branch!
- Use a git command to "undo" the prior two commits on master.  Make sure you **KEEP THE CHANGES IN YOUR WORKING DIRECTORY.**  Just undo the two git commits.  Your `lyrics.txt` file should still contain the 404 lyrics.
- Create a new branch called 404, switch to it, and add and commit the 404 lyrics in your working directory.
- Switch back to master and make sure `lyrics.txt` contains the actual lyrics to Yesterday