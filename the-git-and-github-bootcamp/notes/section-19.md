# Reflogs
Git keeps a record of when the tips of branches and other references were updated in the repo.
We can view and update these reference logs using the git reflog command.

## Limitations!
Git only reflogs on your local activity. They are not shared with collaborators.
Reflogs also expire. Git cleans out old entires after around 90 days, though this can be configured.

## Git Reflog
The git reflog command accepts subcommands show