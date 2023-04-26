# Git Tags
Tags are pointers that refer to particular points in Git history. We can mark a partiular moment in time with a tag. Tags are most often used to mark version releases in projects (v4.1.0, v4.1.1, etc.)
Think of tags as branch references that do NOT CHANGE. Once a tag is created, it always refers to the same commit. It is just a label for a commit.

## The Two Types
There are two types of Git Tags we can use: lightweight and annotated tags.
Lightweight tags are... lightweight! They are just a name/label that points to a particular commit.
Annotated tags store extra meta data including the author's name and email, the date, and a tagging message (like a commit message)

## Semantic Versioning
The semantic versioning spec outlines a standardized versioning system for software releases. It provides a consistent way for developers to give meaning to their software releases (how big of a change is a release??)
Versions consist of three numbers separated by periods
Typically the initial release is 1.0.0
Patch releases normally do not contain new features or significant changes. They typically fix bugs and other changes that do not impact how the code is used. They are represented as the last digit
Minor releases signify that new features or funtionality have been added, but the project is still backwards compatible. No breaking changes. The functionality is optional and should not force users to rewrite thier own code. They are represented as the middle digit.
Major releases signify significant changes that is no longer backward compatible. Features may be removed or changed substanitally

## Viewing Tags
`git tag` will print a list of all the tags in the current repository
We can search for tags that match a particular pattern by using `git tag -l` and then passing in a wildcard pattern. For example, `git tag -l "*beta*"` will pring a list of tags that include "beta" in their name

## Checking Out Tags
To view the state of a repo at a particular tag, we can use `git checkout <tag>`. This puts us in a detached HEAD`

## Creating Tags
To create a lightweight tag, use `git tag <tagname>` By default, Git will create the tag referring to the commit that HEAD is referencing.
Use `git tag -a` to create a new annotated tag. Git will then open your default text editor and prompt you for additional information. Similar to `git commit`, we can use the `-m` option to pass a message directly and forgo the opening of the text editor.

## Tagging Previous Commits
So far we have seen how to tag the commit that HEAD references. We can also tag an older commit by providing the commit hash: `git tag -a <tagname> <commit-hash>`

## Forcing Tags
Git will yell at us if we try to reuse a tag that is already referring to a commit. If we use the `-f` option, we can FORCE our tag through.

## Deleting Tags
To delete a tag, use `git tag -d <tagname>`

## Pushing Tags
By default, the `git push` command does not transfer tags to remote servers. If you have a lot of tags that yo wan to push up at once, you can add the `--tags` option to the `git push` command. This will transfer all of your tags to the remote server that are not already there.