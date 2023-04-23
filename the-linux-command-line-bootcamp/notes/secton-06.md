# Section 06 - Creating Files & Folders

## Important:
- touch Command
- mkdir Command
## Useful: 
- Good vs. Horrible File Names
## Nice to Have
- the file Command

### touch 
touch allows us to create a new file from the command line. If you provide a filename that already exists as a filename it will simply update that file's modification dates. Otherwise it will create a blank file with the name provided. 
For Example: Typing `touch catalog.txt` and submitting will create a new file in the currect directory with the filename of `catalog.txt`

It will always create blank files with or without whatever extension provided.
We can provide a relative or absolute path as a prefix to the filename to create a file anywhere anytime from a single line of code!

Why is touch called touch?
Touch - Change file timestamps
Syntax: touch [OPTION]... FILE...
Update the access and modification times of each FILE to the current time.
A FILE argument that does not exist is created empty, unless -c or -h is supplied.
To me it makes sense to be called touch, and we aren't leveraging touch but rather it's side effect if using to to create a file.

A useful command to determine the file type of a specified file, regardless of it's file extension is by using the `file` command.
It could be beneficial if we were providing a program a file and allow the program to determine what to do with the file.

- Side Bar
    "Multiple Word FILE or FOLDER" could be achieved by Multiple\ Word\ FILE\ or\ FOLDER because `\` tells the machine to ignore the next character programatically, just print it 

### Bad Habits to AVOID when creating files and folders
In general stick to numbers and letters wherever possible. Always avoid spaces. kebab-case is usually best.
Capitalization matters so stick with a clean format.

### mkdir
We can create new directories with the `mkdir` command. It can also create as many folders as the number of arguments increase. Like touch, we can provide a path to the prefix to place the folder anywhere on our machine from the same folder.

# Making Files And Folders Exercise

To get some practice creating files and folders from the command-line, we'll be creating a standard React project file structure.  Don't worry at all if you don't know React, we're just making a bunch of empty files and folders!  

1. Create a new folder called `my-app` [x]
2. Navigate to `my-app` and inside create two new empty files called `README.md` and `package.json` [x]
3. Still inside of `my-app` create a new folder called `public`. Without `cd`-ing into `public`, create an `index.html` file inside of it. [x]
4. Create a new folder called `src` inside of `my-app`.  Navigate inside of it. [x]
5. Using a single line, create the following four files inside of `src`: `App.css`, `App.js`, `index.css`, and `index.js` [x]

Your folder structure should now look like this:

```bash
my-app/
  README.md
  package.json
  public/
    index.html
  src/
    App.css
    App.js
    index.css
    index.js
```

### BONUS
💡 Using a single command, create a new directory inside of `src` called `components`, and inside of that new `components` directory create a new directory called `Navbar`.   Do this using a single command, without first creating the `components` directory. [x]

Your folder structure would now look like this:

```bash
my-app/
  README.md
  package.json
  public/
    index.html
  src/
		**components/
			Navbar/**
    App.css
    App.js
    index.css
    index.js
```

I am using  $null > public/index.html because I am using Power Shell and I don't have this repository on my Linux Machine
I did not have success using this command to create multiple files

CTRL S in Nano is save! (I did not know that)
I also learned that I can open nano in windows by opening a ubuntu terminal from VS Code in this folder! xD


