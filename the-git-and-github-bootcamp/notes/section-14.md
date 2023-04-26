# Git Workflows (for collaboration)

## Centralized Workflow
AKA Everyone Works on Master/Main
AKA The Most Basic Workflow Possible
The simplest collaborative workflow is to have everyone work on the master branch (or main, or any other SINGLE branch)
It is straightforward and can work for tiny teams, but it has quite a few shortcomings!

## The Problem
While it is nice and easy to only work on the master branch, this leads to some serious issues on teams!
- Lots of time spent resolving conflicts and merging code, especially as team size scales up.
- No one can work on anything without disturbing the main codebase. How do you try adding something radically different in? How do you experiment?
- There only way to collaborate on a feature together with another teamate is to push incomplete code to master. Other teamates now have broken code...

## Enter Feature Branches
(DON'T WORK ON MASTER SILLY GOOSE!)
## Feature Branches
Rather than working directly on master/main, all new develpment should be done on separate branches!
- Treat master/main branch as the offical project history
- Multiple teamates can collaborate on a single feature and share code back and forth without polluting the master/main branch
- Master/main branch won't contain broken code (or at lesat, it won't uless someone messes up)
## Feature Branch Naming
There are many different approaches for naming feature branches. Often you will see branch names that include slashes like `bug/fix-scroll` or `feature/login-form` or `feat/button/enable-pointer-events`.
Specific teams and projects usually have their own branch naming conventions. To keep these slides simple and concise, I am just going to ignore those best-practices for now.

## Merging In Feature Branches
At some point the new work on feature branches will need to be merged in to the master branch! There are a couple of options for how to do this...
1. Merge at will, without any sort of discussion with teammate. JUST DO IT WHENEVER YOU WANT. -This is Me
2. Send an email or chat message or something to your team and discuss the changes should be merged in.
3. Pull Requests!

## Pull Requests
Pull requests are a feature built into products like Github and Bitbucket. They are not native to Git Itself.
They allow developers to alert team-members to new work that needs to be reviewed. They provide a mechanism to approve or reject work on a given branch. They also help faciliate discussion and feedback on the specified commits.

## The Workflow
1. Do some work locally on a feature branch
2. Push up the feature branch to Github
3. Open a pull request using the feature branch just pushed up to Github
4. Wait for the PR to be approved and merged. Start a discussion on the PR. This part depends on the team structure

## Recap-ing Pull Requests
Pull requests are a fancy way of requesting chanes from one branch to be merged into another branch.
Tools like Github and Bitbucket allow us to generate pull requests via an online interface (or a CLI with Github Desktop CLI I believe the command is `gh pr <branch>`). Team members can then view the changes and decidde to merge them or reject them. PR's also provide a place to discuss the changes and provide feedback.

## Fork & Clone: Another Workflow
The "fork & clone" workflow is different from anything that we have seen so far. Instead of just one centralized Github repository, every developer has their own Github repository in addition to the "main" repo. Developers make changes and push to their own forks before making pull requests. It is very commonly used on large open-source projects where there may be thousands of contributors with only a couple maintainers.

## Forking
Github (and similar tools) allow us to create personal copies of other peoples' repositories. We call those copies a 'fork' of the original.
We we fork a repo, we are basically asking Github to make a copy of this repo
As with pull requests, forking is not a Git feature. The ability to fork is implemented by Github.

## Now What?
Now that we have forked, we have our very own copy of the repo and we can do whatever we want.
We can clone the fork and make changes, add features, break things, without fear of disturbing the original.
If I do want to share my work, I can at any point make a pull request from my fork to the original repo.

## To Summarize!
1. I fork the original repo on Github
2. I clone my fork to my local machine
3. I add a remote pointing to the original project repo. This remote is commonly named upstream.
4. I make changes and add/commit ona feature branch on my local machine.
5. I push up my new feature branch to my forked repo (usually called origin)
6. I open a pull request to the original project repo containing the new work on my forked repo
7. Hopefully the pull request is accepted and my changes are merged in!

## An Even Briefer Summary
1. Fork the Project 
2. Clone the Fork
3. Add Upstream Remote
4. Do Some Work
5. Push To Origin
6. Open PR