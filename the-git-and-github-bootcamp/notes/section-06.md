# Git Branching

## Contexts
On large projects, we often work in multiple contexts:
1. You are working on 2 different color scheme variations for your website at the same time, unsure of which you like best.
2. You are also trying to fix a horrible bug, but is proving tough to solve. You need to really hunt around and toggle some code on and off to figure it out.
3. A teamate is also working on adding a new chat widget to present at the next meeting. It is unclear if your company will end up using it.
4. Another coworker is updating the search bar autocomplete.
5. Another developer is doing an experimental radical design overhaul of the entire layout to present next month.

## Branches
Branches are an essential part of Git!
Think of branches as alternative timeline for a project.
They enable us to create separate contexts where we can try new things, or even work on multiple ideas in parallel.

If we make changes on one branch, they do not impact the other branches (unless we merge the changes)

## The Master Branch
In git, we are always working on a branch* the default branch name is master
It does not do anything special or have any fancy powers. It is just like any other branch

## Master
Many people designate the master branch as their "source of truth" or the "official branch" for their codebase, but that is left to you to decide.
From Git's perspective, the master branch, is just like any other branch. It does not have to hold the "master copy" of your project.

## Master? Main?
In 2020, Github renamed the default branch from master to main. The default Git branch name is still master, though the Git team is exploring a potential change. We will circle back to this shortly.

## HEAD
We will often come across the term HEAD in Git
HEAD is simply a pointer that refers to the current "location" in your repository. It points to a particular branch reference.
So far, HEAD always points to the latest commit you made on the master branch, but soon we will see that we can move around and HEAD will change!

## Viewing Branches
Use git branch to view your existing branches. The default branch is every git repo is master, though you can configure this. Look for the * which indicates the branch you are currently on.

## Creating Branches
Use git branch <branch-name> to make a new branch based on the current HEAD
This just creates the branch, it does not switch you to that branch

## Switching Branches
Once you have created a new branch, use git switch <branch-name> to switch to it.

## Another way of switching??
Historically, we used git checkout <branch-name> to switch branches. This still works
The checkout command does a million additional things, so the decision was made to add a standalone switch command which is much simpler.
You will see older tutorials and docs using checkout rather than switch but both will work.

## Creating & Switching
Use git switch with the -c flag to create a new branch and switch to it all in one go remember -c for create

## Viewing More Info
Use the -v flag with git branch to view more information about each branch.

### Branching Exercise

1. Make a new folder called `Patronus` [x]
2. Make a new git repo inside the folder (make sure you're not in an existing repo) [x]
3. Create a new file called `patronus.txt` (leave it empty for now) [x]
4. Add and commit the empty file, with the message "add empty patronus file" [x]
5. Immediately make a new branch called `harry` and another branch called `snape` (both based on the master branch) [x]
6. Move to the `harry` branch using the "new" command to change branches. [x]
7. In the `patronus.txt` file, add the following:
    
    ```
    HARRY'S PATRONUS
    
       /|       |\
    `__\\       //__'
       ||      ||
     \__`\     |'__/
       `_\\   //_'
       _.,:---;,._
       \_:     :_/
         |@. .@|
         |     |
         ,\.-./ \
         ;;`-'   `---__________-----.-.
         ;;;                         \_\
         ';;;                         |
          ;    |                      ;
           \   \     \        |      /
            \_, \    /        \     |\
              |';|  |,,,,,,,,/ \    \ \_
              |  |  |           \   /   |
              \  \  |           |  / \  |
               | || |           | |   | |
               | || |           | |   | |
               | || |           | |   | |
               |_||_|           |_|   |_|
              /_//_/           /_/   /_/
    ```
    
8. Add and commit the changes, with the commit message "add harry's stag patronus"
9. Move over to the `snape` branch using the "older" command to change branches.
10.  Put the following text in  the `patronus.txt` file:
    
    ```
    SNAPE'S PATRONUS
                       .     _,
                       |`\__/ /
                       \  . .(
                        | __T|
                       /   |
          _.---======='    |
         //               {}
        `|      ,   ,     {}
         \      /___;    ,'
          ) ,-;`    `\  //
         | / (        ;||
         ||`\\        |||
         ||  \\       |||
         )\   )\      )||
         `"   `"      `""
    ```
    
11. Add and commit the changes on the `snape` branch with the commit message "add snape's doe patronus"
12. Next, create a new branch based upon the `snape` branch called `lily` [x]
13. Move to the `lily` branch [x]
14. Edit the `patronus.txt` file so that it says `LILY'S PATRONUS` at the top instead of
`SNAPE'S PATRONUS` (leave the doe ascii-art alone) [x]
15. Add and commit the change with the message "add lily's doe patronus"
16. Run a git command to list all branches (you should see 4)
17. **Bonus:** delete the `snape` branch (poor Snape)