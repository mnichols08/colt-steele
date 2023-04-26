# Undoing Stuff and Time Travelling

## Checkout
The `git checkout` command is like a Git Swiss Army knife. Many developers think that it is overlaoded, which is what lead to the addition of the git switch and git restore commands.
We can use checkout to create branches, switch to new branches, restore files, and undo history!
we can use `git checkout commit <commit-hash>` to view a previous commit.
Remember, you can use the `git log` command to view commit hashes. We just need the first 7 digits of a commit hash.
Don't panic when you see the following message...
`git checkout d8194d6`

## Detached HEAD ??
You are in 'deatched HEAD' State.