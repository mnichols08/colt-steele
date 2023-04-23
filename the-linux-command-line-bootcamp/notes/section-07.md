# Section 07 - Remove
rm - permanately remove a file or empty directory
rm app.js - removes a file with the name of app.js if it exists
We can chain items to delete such as rm app.js app.css index.js index.css and remove multiple files at once

To remove a directory add -d
to remove directories and their subdirectories recursively use -r
To remove things interactively add -i
Don't forget to chain -ri to recursively but double check on some things before actually removing and can save a lot of headache

We can move items with the mv command. First we specify a file or files as the source and a distination as the argument

To move multiple files or folders we simply type them in sequence such as mv one two three four five desitnation/path/
The destination must exist.

If the destination does not exist, the files we intended to move will be renamed instead.

For example if we try to move a folder to a folder that does not exist, it will create that directory and move the folder specified there effectively moving it.
Another side effect is that if with a file if we move a file to another file to another destination that does not exist it will create the file effectively renaming a file
In addition to moving, we can also rename and move at the same command line with mv SOMETHING.txt ../somewhere/else/SOMETHINGELSE.txt


