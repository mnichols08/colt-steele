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
