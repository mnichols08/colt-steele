# Reflogs
Git keeps a record of when the tips of branches and other references were updated in the repo.
We can view and update these reference logs using the git reflog command.

## Limitations!
Git only reflogs on your local activity. They are not shared with collaborators.
Reflogs also expire. Git cleans out old entires after around 90 days, though this can be configured.

## Git Reflog
The git reflog command accepts subcommands `show`, `exipre`, `delete`, and `exists`. Show is the only commonly used variant, and it is the default subcommand.
`git reflog show` will show the log of a specific reference (it defaults to HEAD).
For example, to view the logs for the tip of the main branch we could run `git reflog show main`

## Reflog References
We can access specific git refs is `name@{qualifier}`. We can use this syntax to access specific ref pointers and can pass them to other commands including checkout, reset, and merge.

## Timed References
Every entry in the reference logs has a timestamp associated with it. We can filter reflog entries by time/date by using time qualifiers like:
- 1.day.ago
- 3.minutes.ago
- yesterday
- Fri,12 Feb 2023 14:06:34 - 0500

## Reflogs Rescue
We can sometimes use reflog entires to access commits that seem lost and are not appearing in git log
