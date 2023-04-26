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

### Stashing Exercise

1. Initialize a new git repo in a folder
2. Create a file called `diary.txt`.  Inside the file, add the following:
    
    ```
    I love my boss
    ```
    
3. Add and commit the changes on the `master` branch
4. Create a new branch called `the-truth`.  Switch to it.
5. In the `diary.txt` file, erase the contents and instead replace it with:
    
    ```
    I HATE MY BOSS
    I HATE MY BOSS
    I HATE MY BOSS
    I HATE MY BOSS
    I HATE MY BOSS
    ```
    
6. Save the file
7. **OH NO!** Your boss is walking towards you! Quick, switch over to the `master` branch!
8. **WHATTT?** The `diary.txt` file still contains our confession?  **Quick, stash the changes before your boss sees!!**
9. Your `diary.txt` file should now only contain "I love my boss"
10. As your boss walks by, add more lies to the `diary.txt` file:
    
    ```
    I love my boss
    I love my boss
    I love my boss
    ```
    
11. Add and commit your changes on the `master` branch.
12. Now that your boss has left, it's safe to get back to the truth! Switch over to the `the-truth` branch.
13. Retrieve the earlier changes that you stashed (I HATE MY BOSS x 5)
14. Add and commit the changes on the `the-truth` branch