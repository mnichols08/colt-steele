# Section 07 - Remove
rm - permanately remove a file or empty directory
rm app.js - removes a file with the name of app.js if it exists
We can chain items to delete such as rm app.js app.css index.js index.css and remove multiple files at once

To remove a directory add -d
to remove directories and their subdirectories recursively use -r
To remove things interactively add -i
Don't forget to chain -ri to recursively but double check on some things before actually removing and can save a lot of headache
