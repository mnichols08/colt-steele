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

We can make copies of files and folders using the cp command
Follows the same syntax as others cp source destination must provide one or more source files or folders and one destination folder

To create a copy of a folder cp Cleanup CopyOfCleanup
This creates a copy of the first folder, most of the time we want to add the recursive option -r to add all folders inside of the folder

# Deleting, Moving & Copying Exercise

## Part 1: Creating The Folders & Files

Before we can delete, move, or copy things...we need things! It's time to get some more practice using `touch` and `mkdir`

Please create a new directory somewhere on your machine called `Bootcamp`.  Inside of it, create the the folders and files indicated below:

```bash
**Bootcamp/**
	**FallCohort/**
		Italo.txt
		Edgar.txt
		Linus.txt
		Sara.txt 
		Silvio.txt
		**Waitlist/**
			Hanna.txt
			Haris.txt
			Netta.txt
	**WinterCohort/**
		Santiago.txt
		Iris.txt
		Naomi.txt
```

- Sadly `Edgar` had to drop out of the course.  Delete the `Edgar.txt` file in `FallCohort`
- This means we now have space in our Fall Cohort to move someone off of the waitlist.  Please move `Netta.txt` from the `Waitlist` folder into the `FallCohort` folder.
- Please delete the `Waitlist` folder and its contents
- It turns out that I misspelled Sara.  She spells her name "Sarah" with an "h" at the end.  Please rename the `Sara.txt` file to `Sarah.txt`
- Unfortunately Italo is having a bit of a personal emergency, and he would like to move to our WinterCohort.  Please move the `Italo.txt` file from `FallCohort` to the `WinterCohort` folder
- Oh no, our entire Winter Cohort had to be cancelled because of a worldwide pandemic :(   We decided to bump all of the scheduled winter students to spring. In the `Bootcamp` directory create a copy of the `WinterCohort` folder called `SpringCohort`
- Please rename the WinterCohort folder to `WinterCohortCANCELLED`
- Oh no! We're going out of business. Please delete the entire `Bootcamp` directory 😢
