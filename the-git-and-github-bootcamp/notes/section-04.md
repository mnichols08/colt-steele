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

Our Actual First Git Command!
Use `git init` to create a new git repository.
I am skipping this step but I understand the concept

### Committing Basics Exercise

1. Create a new folder called `Shopping`
2. Initialize a new git repo inside of the `Shopping` folder (make sure you're not already inside of a Git repo!)
3. Make a new file called `yard.txt`
4. Make another new file called `groceries.txt`
5. Make a commit that includes both empty files.  The message should be "create yard and groceries lists"
6. In the `yard.txt` file, add the following changes:
    
    ```
    - 2 bags of potting soil
    - 1 bag of worm castings
    ```
    
7. In the `groceries.txt` file, add the following:
    
    ```
    - 4 tomatoes
    - 6 shallots
    - 1 fennel bulb
    ```
    
8. Make a new commit, including **ONLY the changes from the `groceries.txt` file.**  The commit message should be "add ingredients for tomato soup"
9. Make a second commit including **ONLY the changes to the `yard.txt` file.**  It should have the commit message "add items needed for garden box"
10. Next up, add the following line to the end of `groceries.txt`
    
    ```
    - couple of seed potatos
    ```
    
11. In the `yard.txt` file, change the first line so that it says "**3** bags of potting soil" instead of "2 bags of potting soil"
    
    ```
    - 3 bags of potting soil
    - 1 bag of worm castings
    ```
    
12. **Make a commit that includes the changes to BOTH files.**  The message should read "add items needed to grow potatoes"
13. **Use a Git command to display a list of the commits. You should see 4!**