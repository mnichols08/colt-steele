# Finding Things

	locate
	The locate command performs a search of pathnames across our machine that match a given substring and then prints out any matching names.
	It is nice and speedy because it uses a pre-generated database file rather than searching the entire machine.
	For example, `locate chick` ill perform a search for all files that contain chick in their name.
	
	locate options
	The -e option will only print entries that actually exist at the time loate is run
	The -i option tells locate to ignore casing
	The -l or --limit option will limit the number of entires that locate retrieves

	find
	The locate command is nice and easy but it can only do so much! The find command is far more powerful!
	Unlike locate, find does not use a datebase file.
	By default, find on it's own will list every single file and directory nested in our current working directory.
	We can also provide a specific folder. `find friends/` would print all the files and subdirectories inside the friends directory (including nested folders)

	finding by type
	We can tell find to only find by file type: only print files, directories, symbolic links, etc using the -type options
	`find -type d` - will limist the search to directories
	`find -type f` will limit the search to files

	finding by name
	We can provide a specific pattern for find to use when matching filenames and directores with the `-name` options. We need to enclose our pattern in quotes.
	To find all files on our Desktop that end in the .txt extension, we could run `find ~/Destop -name "*.txt"
	Use the -iname option for case insensitive search

	Counting Results
	`find -name "*.htmls" | wc -l` => We can pipe the output of find to other commands like word count. Use the -l option to count the number of lines (each result from find is its own line)
	
	finding by size
	We can use the -size option to find files of a specific size. For example, to find all files larget than 1 gigabyte we could run `find -size +1G`
	To find all files under 50 mb we could run `find -size -50M`
	To find all files that are exactly 20kb, we could run `find -size 20k`

	finding by owner
	We can use the -user option to match files and directories that belong to a particualar user. `find -user Mikey`

	Timestamps
	mtime, or modification time, is when a file was last modified AKA when its contents last changed.
	ctime, or change time, is when a file was last changed. This occurs anytime mtime changes but also when we rename a file, move it, or alter permissions.
	atime, or access time, is updated when a file is read by an application or a command like cat.

	Finding By Time
	We can use the -mtime num option to match files/folders that were last modified num*24 hours ago. `find -mmin -30`
	`find -mmin -20` matches items that were modified LESS than 20 minutes ago.
	`find -mmin + 60` matches items that were modified MORE than 60 minutes ago.
	`find -amin n` will find files that were last accessed n minutes ago. We can specify +n for "greater than n minutes ago" and -n for "less than n minutes ago"
	`find -anewer <file>` will find files that have been accesses more recently than the provided file
	`find -cmin -20` matches items that were changed LESS than 20 minutes ago
	`find -cmin + 60` matches items that were changed MORE than 60 minutes ago.

	Logical Operators
	We can use the -and, -or, and -not operators to create more complex queries.
	`find -name "*chick*" -or- -name "*kitty*"`
	`find -type -f -not -name "*.html"`

	User Defined Actions
	We can provide find with our own action to perform each matching pathame.
	The syntax is `find -exec command {}; `
	The {} are placeholder for the current pathname (each match), and the semicolon is required to indicate the end of the command.
	`find -name "*broken" -exec rm '{}' ';'` - To delete every file that starts with contains "broken" in its file name
	Note that we need to wrap the {} and ; in quotes because those characters have special meaning otherwise
	`find -type f -user Mikey -exec ls -l '{}' ';'` finds all files that are owner by the user Mikey and then it lists out the full details for each match using ls -l
	`find -type f -name "*.html" -exec cp '{}' '{}_COPY' ';' finds all files that end with .thml and creates of a copy of them using the copy command with the suffix of COPY

	xargs
	xargs reads items from standard input, separated by blanks (spaces or newlines) and then executes a command using those items
	The mkdir command expects us to pass arguments. It does not work with standard input, so this example does NOT make any folders for us
	`echo "hello" "World" | mkdir` => mkdir: missing operand
	We can instead add in the xargs command, which will accept the standard input coming from echo and pass them as arguments to mkdir
	`echo "hello" "world" | xargs mkdir

	# Find Exercise

Please download the following zip file, unzip it, and navigate to the `Cases/` directory.

[Cases.zip](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/06091973-41ef-4e9f-bcf8-e3f2701d43f3/Cases.zip)

**Note: in order for this exercise to work out, please avoid modifying any of the case files!**

## Your Task

Welcome detective! The `Cases` folder contains a couple thousands case files, both open and closed.  Please use the `find` command to assist you in the following tasks:

1. Using `find` (and another command), count the number of case files that include "closed", in lowercase, in their name. You should find **980** cases. [x] - `echo 'closed cases:' > ../Cases.txt | find -name "*closed*" 2>> ../CasesErrors.log | wc -l >> ../Cases.txt 2>> ../CasesErrors.log`
2. Oh no, one of our new detectives labels his cases using "CLOSED" in all caps.  Find the 3 cases that have "CLOSED" in their name. [x] - `echo 'CLOSED cases:' >> ../Cases.txt | find -name "*CLOSED*" 2>> ../CasesErrors.log | wc -l >> ../Cases.txt 2>> ../CasesErrors.log`
3. Get a total count of all closed cases that include "closed" in their name, uppercase or lowercase.   You should get a count of 983! [x] - `echo 'combined open and CLOSED cases:' >> ../Cases.txt | find -iname "*closed*" 2>> ../CasesErrors.log | wc -l >> ../Cases.txt 2>> CasesErrors.log` 
4. Get a count for the total number of **open** cases with odd numbered case numbers (find the open cases that have a 1,3,5,7, or 9 as the last digit in their case number).  You should get 519 cases. [ ]
5. Find the three empty cases [x] - `echo 'Empty Cases:' >> ../Cases.txt | find -empty >> ../Cases.txt 2>> CasesErrors.log`
6. Most of these files are quite small, but there are 3 pretty large case files.  Find the three files that are larger than 20k in size [x] - `echo 'three larger case files:' >> ../Cases.txt | find -size +20k >> ../Cases.txt 2>> CasesErrors.log` 
7. Find the one case file that is larger than 150k and is closed [x] - `echo 'Case file larger than 150k:' >> ../Cases.txt | find -iname "*closed*" -size +150k >> ../Cases.txt 2>> CasesErrors.log`
8. No one has touched these case files in years, or at least no one should have touched these files, but sadly some corrupt detective recently tampered with one of the files.  Sometime today he changed a single case from "closed" to "open" to spite an enemy of his.   Find the one case that has been modified more recently than the `yesterday.txt` file.  Watch the exercise intro video if you're confused!   You may need to read the man pages to find the correct command.