# Comparisons With Git Diff

## Git Diff
We can use the git diff command to view changes between commits, branches, our working directory, and more!
We often use git diff alongside commands like git status and git log, to get a better picture of a repository and how it has changed over time.
Without additional options, git diff lists all of the changes in our working directory that are NOT staged for the next commit
`git diff HEAD` lists all changes in the working tree since your last commit.

## Compared Files
For each comparison, Git explains which files it is comparing. Usually this is two versions of the same file. Git also declares one file as "A" and the other as "B".

## File Metadata
You really do not need to care about the file metadata
The first two numbers are the hashes of the two files being compared. The last number is an internal file mode identifier.

## Markers
File A and File B are each assigned a symbol.
- File A gets a minus sign (-)
- File B gets a plus sign (+)

## Chunks
A diff won't show the entire contents of a file, but instead only shows portions or "chunks" that were modified.
A chunk also includes some unchanged lines before and after a change to provide some context.
Each chunk starts with a chunk header, found between @@ and @@.
From file a, 4 lines are extracted starting from line 3.
From file b, 5 files are extracted starting from line 3.

## Changes
Every line that changed between the two files is marked with either a + or - symbol
Lines that begin with - come from file A
Lines that begin with + come from file B

## git diff
git diff --staged or --cached will list the changes between the staging area and our last commit.

## Diff-ing specific files
We can view the changes within a specific file by providing git diff with a filename

## Comparing Branches
git diff branch1..branch2 will list the changes between the tips of branch1 and branch2

## Comparing Commits
To compare two commits, provide git diff with the commit hashes of the commits in question.

### Git Diff Exercise

This exercise comes with a starter repo that you will need to clone down to your machine.  We will be working with two bands: Queen and Fleetwood Mac and their various lineups over the years.

## Part 1: Setup

Please run the following commands from your terminal.  Make sure you are not inside of a Git repo.

```
git clone https://github.com/Colt/git-diff-exercise
```

- Change into the newly created folder called `git-diff-exercise`.  You will be on a branch called `current` by default.
- Run `git switch 1970s`
- You should now have two branches that you can move between: `current` and `1970s` Each branch contains two files: `queen.txt` and `fleetwoodmac.txt`

## Part 2: The Diffs

1. Compare the difference between the `1970s` branch and the `current` branch across all files [x]
2. Compare the difference between the `1970s` branch and the `current` branch but only for the queen.txt file [x]
3. Switch over to the `current` branch if you are not currently on it.   Run a diff to compare the current HEAD to the previous commit (you could use the commit hash or reference HEAD's parent commit) [x]
4. While on the `current` branch, change the `queen.txt` file by replacing Adam Lambert with your own name.  Save the change.  Add `queen.txt` to the staging area.  DO NOT COMMIT YET! [x]
5. Edit the `fleetwoodmac.txt` file, changing the lead singer from Stevie Nicks to Stevie Chicks (one of my chickens).  Save the file, but do not stage it. [x]
6. Run a diff that would reveal the unstaged changes in the working directory (you should see only the change to `fleetwoodmac.txt` printed out) [x]
7. Run a diff that would reveal only the staged changes (you should only see the change to `queen.txt` printed out) [x]
8. Run a diff that prints all changes (staged and unstaged) since the prior commit (you should see both changes printed out) [x]