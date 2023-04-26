# Git Behind The Scenes

## What is in .git??
## Config
The config file is for...configuration. We have seen how to configure global settings like our name and email across all Git repos, but we can also configure things on a per-repo basis.

## Refs folder
Inside of refs, you will find a heads directory. `refs/heads` contains one file per branch in a repository. Each file is named after a branch and contains the hash of the commit at the tip of the branch.
For example `refs/heads/master` contains the commit hash of the last commit on the master branch.
Refs also contains a `refs/tags` folder which contains one file for each tag in the repo.

## Head
HEAD is just a text file that keeps track of where HEAD points.
If it contains `ref/heads/master`, this means that HEAD is pointing to the master branch.
In detached HEAD, the HEAD file contins a commit hash instead of a branch reference

## Index
The index file is a binary file that contains a list of the files the repository is tracking. It store the file names as well as some metadata for each file. Not that the index does NOT store the actual contents of the files it contains references to files.
## Objects Folder
The objects directory contains all the repo files. This is where Git stores the backups of files, the commits in a repo, and more.
The files are all compressed and encrypted, so they will not look like much!
## 4 Types of Git Objects
1. commit
2. tree
3. blob
4. annotated tag

## Time Out! (We need to talk about hashing)
Hashing functions are functions that map input data of some arbitrary size to fixed-size output values
'I love Chickens' => D 7 0 F F 0 A B 9 A 2 3 E C 5 D B A 9 0 7 5
B 0 E 4 D E D E 8 C 2 9 7 2 B A 9 3 3 D 6 D
5 A D F 3 A 4 2 A B B 6 E 0 D 7 A 2 D A
'LOL' => 0 7 1 2 3 E 1 F 4 8 2 3 5 6 C 4 1 5 F 6 8 4 4
0 7 A 3 B 8 7 2 3 E 1 0 B 2 C B B C 0 B 8 F
C D 6 2 8 2 C 4 9 D 3 7 C 9 C 1 A B C

## Cryptographic Hash Functions
1. One-way function which is infeasible to invert
2. Small change in input yields large change in the output
3. Deterministic - same input yeields same output
4. Unlikely to find 2 outputs with the same value

## SHA-1
Git uses a hashing function called SHA-1 (thought hti sis set to change eventually)
- SHA-1 always generates 40 digit hexadecimal numbers
- The commit hashes we have seen a million times are the output of SHA-1

## Git Database
Git is a `key-value data store`. We can insert any kind of content into a Git repository, and Git will hand us back a unique key we can later use to retrieve that content.
These keys that we get back are SHA-1 checksums.

## Let's Try Hashing
The `git hash-object` command takes some data, stores in our `.git/objects` directory and gives us back the unique SHA-1 hash that refers to that data object.
In the simplest form (shown on the right), Git simply takes some content nd returns the unique key that WOULD be used to store our object. But it does not actually store anything.
The `--stdin` option tells `git hash-object` touse the content from `stdin` rather than a file. In our example, it will hash the word 'hello'.
The echo command simply repeates whatever we tell it to repeat to the terminal. We pipe the output of `echo` to `git has-object`.
`echo 'hello' | git hash-object -stdin -w`
Rather than simply outputting the key that git would store our object under, we can use the -w option to tell git to actually write the object to the database.
After running this command, check out the contents of `.git/objects`
`git cat-file -p <object-hash>`
Now that we have data stored in our Git object database, we can try retrieving it using the git cat-file command.
The -p option tells Git to pretty print the contents of the object based on its type.

## Blobs 
Git blobs (binary large object) are the object type Git uses to store the contents of files in a given repository. Blobs don't even incude the filenames of each file or any other data. They just store the contents of a file!

## Trees
Trees are Git objects used to store the contents of a directory. Each tree contains pointers tha can refer to blobs and to other trees.
Each entry in a tree contains the SHA-1 hash of a blob or tree, as well as the mode, type, and filename

## Viewing Trees
`git cat-file -p master^{tree}`
Remember that `git cat-file` prints out Git objects. In this example, the `master^{tree}` syntax specifies the tree object that is pointed to by the tip of our master branch.

## Commits
Commit objects combine a tree object along with information about the context that led to the current tree. Commits store a reference to parent commit(s), the author, the commiter, and of course the commit message!
When we run git commit, Git creates a new commit object whose parent is the `current HEAD commit` and whose tree is th ecurrent context of the index.

