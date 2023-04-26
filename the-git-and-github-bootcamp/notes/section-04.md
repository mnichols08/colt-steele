# Git Basics

## A Quick High-Level Conceptual Overview
### Repository
A Git "Repo" is a workspace which tracks and manages files within a folder.
Anytime we want to use Git with a project, app, etc. we need to create a new git repository. We can have as many repos on our machine as needed, all with separate histories and contents.

### Committing
The most important Git feature!
Making a commit is similar to making a save in a video game. We are taking a snapshot of a git repository in time.
When saving a file, we are saving the state of a single file. With Git, we an save the state of multiple files and folders together.

### The Basic Git Workfloow
1. Work on Stuff
- Make new files, edit them, delete some things, etc. >
2. Stage Changes
- Group specific changes together, in preparation of commiting > 
3. Commit
- Commit everything that was just staged

### Our First Git Command!
`git status` gives information on the current status of a git repository and its contents
It is very useful, but at the moment we don't actually have any repos to check the status of! (well I do but that's neither here nor there)

If we try it...
`git status` => Your branch is ahead of 'origin/the-git-and-github-bootcamp' by 1 commit.