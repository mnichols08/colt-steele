# Expansion & Substitution

## Slides 
	echo - The echo command is very simple. It simply displays text that we pass to it. We will be using it to demonstrate some concepts in this section. 
	It is particularly useful in shell scripts (we cover them later), when we want to output something to the screen from within a file.

	Wildcard Characters (aka globbing patterns)
	We can use special wildcard characters to build patterns that can mathc mulitple filenames at once.
	The asterisk (*) character represents zero or more characters in a filename. For example...
	- `ls *.html` will match any files that end with .html like index.html and navbar.html
	- `cat blue*` will match any files that start with blue, like blue.html or bluesteel.js

	The ? Wildcard
	The question mark (?) character represents any single character.
	- `ls app.??` will match any files names app that end with two character file extensions like app.js or app.py but NOT app.css
	- `ls pic?.png` will match pic1, pic2, pic3, and also picA, picx, etc.png.

	Range Wildcards
	Inside of square brackets ([]) we can specify a range of characters to match.
	- `ls pic[123].png` will only match pic1.png, pic2.png, and pic3.png
	- `ls file[0-9]` will match file1, up to file9
	- `ls [A-F]*` will match any files that begin with a capital A-F 

	Negating Ranges
	Inside of square brackets ([]) we can specify a range of characters to NOT match, by using a caret (^).
	- `ls [^a]*` will match any files that do NOT start with the character "a"
	- `ls [^0-9]*` will match any files that do NOT start with a numeric digit

	Character Classes
	We can also use predefined named characters classes:
	[:alpha:] - alphabetic characters, upper and lowercase
	[:digit:] - digits 0-9
	[:lower:] - lowercase characters
	[:upper:] - uppercase characters
	[:blank:] - blank characters such as space and tab
	[:punct:] - punctuation characters
	[:alnum:] - alphanumeric characters (alpha+digit)

	Brace Expansion
	Used to generate arbitary strings. Basically, it will generate multiple strings for us based on a pattern. we provide a set of strings inside of curly braces ({}), as well as optional surrounding prefixes and suffixes.
	The specified strings are used to generate all possible combinations with the optional prefixes and suffixes.
	For example, `touch page{1,2,3}.txt` will generate three new files: page1.txt, page2.txt, page3.txt.
	
	Ranges
	We can provide a numeric range, which will be used to generate a sequence. In this example, `jan{1..31}` will be expanded to jan1 through j31.
	We can provide a third value which defines the interval for the range. In this example, `echo {2..10..2}` will print out the numbers 2, 4, 6, 8, 10.
	We can even specify alphabetical ranges. `touch group-{a..e}.txt` will generate the files group-a - group-e.

	Brace Expansion Examples
	`echo {a,b,c}{1,2,3}` => a1, a2, a3, b1, b2, b3, c1, c2, c3
	`echo {b,r}{eef,at,ag}` => beef, bat, bag, reef, rat, rag
	
	Nested Brace Expansion Example
	`echo {x,y{1..5},z}` => xy1y2y3y4y5z

	Arithmetic Expansion
	The shell will perform arithmetic via expansion using the S((expression)) syntax. Inside the parenthesis, we can write arithmetic expressions using: 
	- + addition
	- - Subtration
	- * Multiplication
	- / Division
	- ** exponentiation
	- % modulo (remainder operator)
	
	Examples
	`echo $((10+7))` => 17
	`echo $((3*13))` => 39
	`echo $((10/3))` => 3
	The shell only performs integer arithmetic, so the result is always a whole number

	Command Substitution
	We can use the $(command) syntax to display the output of another command.
	For example `echo "today is $(date)"` will concenate a useful string before today's date

	Quoting
	In this example, our large whitespace is ignored because the shell performs something called word splitting.
	`echo look at	me` => look at me
	In this example, we only see "holy" printed out because the shell thinks we are referencing a variable called hit. It cannot find a value for hit, so it subsitutes an empty string instead
	`echo holy $hit` => holy

	Double Quotes
	If we wrap text in double quotes, the shell will respect our spacing and ignore special characters except for dollar sign, backslash, and backtick.
	Pathname expansion, brance expansion, and word splitting will be ignored. However, command substitution and arithmetic expansion is still performed because dollar signs still have meaning inside double quotes.
	
	Single Quotes
	Use single quotes to suppress all forms of substitution
	`echo "$((2+2)) is 4` => 4 is 4
	`echo '$((2+2)) is 4` => $((2+2)) is 4

	Escaping
	To selectively prevent expansion, or substitution for specific characters, we can prefix them with a single backslash.
	We can use this to reference special characters that normally have meanings inside of filenames.

## Video Notes
Important: pathname expansion, brace expansion, quoting
Useful: Command Substitution
Nice To Have: Arithmetic expansion, tilde expansion

Echo is essentially a way to provide a visual experience to the user whether it is yourself or someone else. It lets us print to the terminal.

### Exercise
# Expansion Exercise

## Part 1 - Making Some Files

1. Create the following 60 files **using a single command** with the powers of expansion! [x] - `touch {morning,afternoon}-day-{1..30}`
    
    ```bash
    
    morning-day-1
    morning-day-2
    ...
    morning-day-30
    
    afternoon-day-1
    afternoon-day-2
    ... 
    afternoon-day-30
    ```
    
2. For this next bit, you'll need to use the following command: `date +"%m-%d-%y"` This command will print out the current date using the format *month-day-year*, like **09-19-21**. Use this command to create a new file with the name ***todos-DATE.txt***, where DATE is the output of the above date command.  For example, if we ran the command on September 19th 2021, the resulting file would be named `todos-09-19-21.txt`. [x] - `date +"%m-%d-%y" > todos-$(date +"%m-%d-%y").txt`

## Part 2

Using the files that we created in the previous section...

- List out all the files that end with the number `9`
- List out all the filenames where the second to last character is `1`
- List out all the files that start with afternoon and then end with the number `7`
- Make a new folder called `Mornings`, and move all the files that start with `morning` inside of it.

## Part 3

- Using a SINGLE command (with expansion), create the following folder structure.  You will need to use the `-p` option with mkdir!

```bash
Year/
	Winter/
		Yard/
		House/
	Spring/
		Yard/
		House/
	Summer/
		Yard/
		House/
	Fall/
		Yard/
		House/
```

- Finally, in each of the `Yard/` and `House/` Directories create a `todos.txt` file and a `done.txt` file.  Do this with a single line, without changing directories!  Use expansion! The resulting folder/file structure should look like this:

```bash
Year/
	Winter/
		Yard/
			todos.txt
			done.txt
		House/
			todos.txt
			done.txt
	Spring/
		Yard/
			todos.txt
			done.txt
		House/
			todos.txt
			done.txt
	Summer/
		Yard/
			todos.txt
			done.txt
		House/
			todos.txt
			done.txt
	Fall/
		Yard/
			todos.txt
			done.txt
		House/
			todos.txt
			done.txt
```
