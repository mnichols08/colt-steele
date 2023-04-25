# Grep
`grep <pattern> <file>`
The `grep` command searches for patterns in each file's contents. Grep will print each line that matches a pattern we provide.
For example, `grep "chicken" animals.txt will print each line from the animals.txt file that contains the pattern "chicken"

Case Insensitive
Use the -i option with grep to make the search case insensitive
`grep -i "Chapter" book.txt will print all matching lines from the book.txt file that contain the word "chapter" in upper or lowercase

Word Search
Use the -w option to ensure that grep only matches words, rather than fragments located inside of other words. A word is defined by nonword characters on either side (start of line, space, end of line, punctuation, etc.)
`grep -w "cat" book.txt` would match cat but not catheter

Recursive Search
Use the -r option to perform a recursive search which will include all files under a directory, subdirectories and their files, and so on.
If we do not specify a starting directory, grep will search the current working directory.
grep -r "chicken" will search the current working directory and any nexted directories for lines that contain "chicken"

Regex Crash Course
We can provide regular expressions to `grep`. Regular expressions help us match complex patterns, BUT the syntax does differ from what we have seen so far.
- `.` - matches any single character
- `^` - matches the start of a line
- `$` - matches the end of a line
- `[abc]` - matches any character in the set
- `[^abc]` - matches any character NOt in the set
- `[A-Z]` - matches characters in range
- `*` - repeat previous expression 0 or more times
- `\` - escape meta-characters

