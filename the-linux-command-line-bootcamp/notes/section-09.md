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

`wc <filename>` - prints out 3 numbers - lines, words, bytes in a file
`wc <filename> -l` - lines
`wc <filename> -c` - bytes
`wc <filename -m` - characters
The word count command can tell us the number of words, lines, or bytes in files. By default it prints out three numbers: the lines, words, and bytes in a file.
We can use the -l option to limit the output to eh number of lines.
The -w option limits the output to the number of words in the file.

`sort <filename>` - would print each line from a file sorted in alphabetical order
The sort command outputs the sorted contents of a file (it does not change the file itself). By default, it will sort the lines of a file alphabetically.
 -r can be used to return in reverse not to be confused with -R for random-sort
 -n for numeric sort
 -u tells sort command to ignore duplicate values
 -k <number> to specify a particular column that we want to sort by using a field number after
 -kn <number> to sort by a number in a particular column

# Working With Files Exercise

[[FilesExercise.zip](http://filesexercise.zip)](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8c10648f-ff91-46f3-a922-a2c4983c10d1/FilesExercise.zip)

Once you have downloaded the above zip file, unzip it! It contains two files: `poem.txt` and `purchases.txt`

## Part 1

- Use a command to print out the entire contents of the `poem.txt` file. Use an option so that the output also includes line numbers.
- That is a headache to read all at once! Read poem.txt using `less` instead.
    - Scroll down one line at a time
    - Scroll up one line at a time
    - Scroll down one "page" at a time
    - Scroll up one "page" at a time
- Search within less for the term "Dog".  Can you find the line that contains it?
    - **BONUS:** can you run a case-insesitive search?  The poem contains both "dog" and "Dog" on separate lines.
- Now it's time to do some research! Find the option to tell less to open with lines numbers displayed. Open `poem.txt` this way
- Then find the "command" you can type into less to go to exactly 50% of the way through the file.
- Use a command to find the number of **words** in `poem.txt`
- Run a command to print out the first 4 lines of `poem.txt`
- Run a command to print out the last 8 lines of `poem.txt`

## Part 2

- Run a command to print out the lines in `purchases.txt` in reverse order (last line printed first)
- Run a command to print out the lines in `purchases.txt`, sorted alphabetically.
- Run a command to count the number of **lines** in `purchases.txt`
- Run a command to print out the lines in `purchases.txt`, sorted by the price (the final column) in the dataset in REVERSE order (highest price to lowest price)
