# Section 9 - Working With Files
Useful Terms - Cat, Less, Head, Tail, Sort, WC

cat - The cat command concatenates and prints the contents of files.

`cat <filename>` - will read the contents of a file and print them out. For example, cat instructions.txt will read in from the instructions.txt file and then print the contents out to the screen.

It is sort of like ls but lists the contents of a file directly in the terminal. It can be useful if you are working on the command line of a server to view the contents of a file quickly without opening a text editor and reading it and then exiting.

The concatenation part comes from cat. It allows us to take multiple files as inputs and output a single phrase

`less <filename>` - will read the contents of a file in a way that allows the user to navigae up and down and also have the ability to search. It is a lot like a pdf reader - not an editor.
- With less open we have access to a few commands:
	- space or f to go to next page
	- b to to back to previous page
	- enter or down to scroll line by line
	- forward slash / followed by a pattern to search
	- q to quit
`tac <filename>` - just like cat, but in reverse

`rev <filename>` - reverse each line

`head <filename>` - would print the first ten lines of a file
The head command prints a portion of a file, starting from the beginning of the file. By default, it prints the first 10 lines of a file.

`tail <filename>` - would print the final ten lines of a file
The taile command is the opposite of the head command

Both `head` and `tail` can be provided an option of -n <number> and provide a number of lines to display instead of defaulting to 10 we can skip the -n and provide just a -<number> as well
In addition, there is a `-c` option which is used to display the last number of bytes
`tail` can be provided an option of `-f` to await changes at the end of a file. It is particularly useful for viewing logs as it hangs up the terminal but allows the user to monitor incoming changes in realtime
