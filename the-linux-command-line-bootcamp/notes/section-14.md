# Grep
`grep <pattern> <file>`
The `grep` command searches for patterns in each file's contents. Grep will print each line that matches a pattern we provide.
For example, `grep "chicken" animals.txt will print each line from the animals.txt file that contains the pattern "chicken"

Grep is case sensitive by default.

Recursive Search
Use the -r option to perform a recursive search which will include all files under a directory, subdirectories and their files, and so on.
If we do not specify a starting directory, grep will search the current working directory.

grep -r "chicken" will search the current working directory and any nexted directories for lines that contain "chicken"