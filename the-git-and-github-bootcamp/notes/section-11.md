# Github Basics

## What is Github?
Github is a hosting platform for git repositories. You can put your own Git repos on Github and access them from anywhere and share them with people around the world.
Beyond hosting repos, Github also provides additional collaboration features that are not native to Git (but are super useful). Basically, Github helps people share and collaborate on repos.

## Git
Git is the VCS that runs locally on your machine
## Github
Github is a service that hosts git repos.

## Github is not your only option...
There are tons of competing tools that provide similar hosting and collaboration features, including Gitlab, BitBucket, and Gerrit.
With that said...
### It is very popular!
Founded in 2008, Github is now the world's largest host of cource code. In early 2020, Github reported having over 40 million users and over 190 million repositories on the platform.

## It is Free!
Github offers its basic services for free! While Github does offer paid Team and Enterprise tiers, the basic Free tier allows for unlimited public and private repos, unlimited collaborators, and more!
### Why You should Use Github (or at least know how to use it)
## Collaboration
If you ever plan on working on a project with at least one other person, Github will make your life easier! Whether you are building a hobby project with your friend or you are collaborating with the entire world, Github is essential!

## Open Source Projects
Today Github is THE home of open source projects on the Internet. Projects raning from React to Swift are hosted on Github.
If you plan on contributing to open surce projects, you need to get comfortable with working with GitHub.

## Exposure
Your Github profile showcases your own projects and contributions to other's projects. It ca act as a sort of resume that many employers will consult in the hiring process. Additionally, you can gain some clout on the platform for creating or contributing to popular projects.

## Stay Up To Date
Being active on Github is the best way to stay up to date with the project tools and tools you rely on. Learn about upcoming changes and the decisions/debate behind them.

## Cloning
So far we have created our own Git Repositories from a scratch, but we want to get a local copy of an existing repository instead.
To do this we can clone a remote repository hosted on Github or similar websites. All we need is a URL that we can tell Git to clone for use.
To clone a repo simply run `git clone <url>`
Git will retrieve all of the files associated with the repo and copy them to your local machine.
In addition, Git initializes a new repository on your machine, giving you acces to the full Git history of the cloned project.

## Permissions?
Anyone can clone a repository from Githhub, provided the repo is public. You do not need to be an owner or collaborator to clone the repo locally on your machine. You just need the URL from Github. Pushing up your own changes to Github repo does require permissions.

## We are not limited to Github Repos!
`git clone` is a standard git command.
It is NOT tied specifically to Github. We can use it to clone repositories that are hosted anywwhere! It just happens that most are hosted on Github these days.

## SSH Keys
You need to be authenticated on Github to do certain operations, like pushing up code from your local machine. Your terminal will prompt you every single time for your Github email and password unless..
You generate and configure an SSH Key! Once configured, you can connect to Github witout having to supply your username and password.
## How Do I get My code on GitHub?
### Option 1: Existing Repo
If you already have an existing repo locally that you want to get on Github...
- Create a new repo on Github
- Connect your local repo (add a remote)
- Push your changes to Github
### Option 2: Start From Scratch
If you have not begun work on your local repo, you can...
- Create a brand new repo on Github
- Clone it down to your machine
- Do some work locally
- Push up your changes to Github

## Pushing
To get your own changes and Git history up on Github, we need to PUSH them up. The typical workflow looks something like this: 
- Make some changes locally
- Add and commit those changes
- Repeat...
- Push new Commits to Github

## Remote
Before we can push anything to Github, we need to tell Git about our remote repository on Github. We need to set up a destination to push up to.
In Git we refer to these destinations as remotes. Each remote is simply a URL where a hosted repo lives.

## Viewing Remotes
To view any existing remotes for your repo, we can run `git remote` or `git remote -v` (verbose, for more info)
This just display a list of remotes. If you have not added any remotes yet, you will not see anything!

## Adding a New Remote
A remote is really two things: a URL and a label. To add a new remote, we need to provide both to Git.
`git remote add <name> <url>`

## Origin?
Origin is a conventional Git remote name, but it is not at special. It is just a name for a URL.
When we clone a Github repo, the default remote name setup for us is called origin. You can change it. Most people leave it.

## Checking Our Work
Try viewing your remotes with `git remote -v` and you should see a remote showing up!
Remember by setting up a remote we are just telling Git about a remote URL. We have not "communicated" with the Github repo at all yet.

## Other Commands
They are not commonly used, but there are commands to rename and delete romotes if needed.
`git remote rename <old> <new>`
`git remote remove <name>`

## Pushing
Now that we have a remote set up, let's push some work to Github! To do this we need to use the `git push` command.
We need to specify the remote we ant to push up to AND the specific local branch we want to push up to that remote.
## An Example
`git push origin master` tells git to push up the master branch to our origin remote

## Workflow Recap
Remember to follow these basic steps:
- Create a new empty repo on Github
- Copy the repo URL
- Add a remote to your local repo, using the URL
- Push changes to the remote

## Github Basics Exercise

1. Create a new repository locally on your machine. [x]
2. Create a new Github repository. Name it whatever you want. [x]
3. Connect your local repo to the Github repo. [x]
4. Optional: rename the default branch from master to main. [x]
5. Make a new file called `favorites.txt`  Leave it empty. Make your first commit on the `main` branch. [x]
6. Push up your `main` branch to Github! Make sure you see your empty `favorites.txt` file on Github.
7. Next, create two branches: `foods` and `movies`
8. Switch to the `foods` branch.  Add three (or more) of your favorite foods to the `favorites.txt` file.  Add and commit your changes on the `foods` branch.
9. Switch to the `movies` branch and add three or more of your favorite movies to the `favorites.txt` file.  Add and commit your changes on the movies branch.
10. Push up your `foods` branch to Github. Make sure you see it on Github!
11. Push up your `movies` branch to Github.  Make sure you see it on Github!
12. Merge the `foods` branch into the `main` branch.  Then merge the `movies` branch into the `main` branch.  If necessary, resolve conflicts so that you end up with your favorite foods and favorite movies in the same `favorites.txt` file. 
13. Push up the latest work on your `main` branch to Github.
