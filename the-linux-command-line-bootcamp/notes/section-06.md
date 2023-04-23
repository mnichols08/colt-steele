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

If learned and used appropriately, Nano can increase productivity but may not be worth mastering.

I did just find that even if my computer crashes, while editing a file within nano, that a file .swp remains in the folder and I was able to retrieve this section of coude which I previous lost xD

## Shortcuts

There are all sorts of shortcuts that I can not seem to get to work so I am quite confused at this point. I imagine it is because I am in WSL inside of VS Code. It works as it does in the videos just fine when opening up a new Ubuntu Shell outside of VS Code.

1. Ctrl + W - Search Forwards
2. M + C - Case Sensitive  
3. Ctrl + \ - Replace
4. Ctrl + T - Spell No Checkify disabled by default - even enabled it does not work for me it says error with aspell

# Nano Exercise

[NanoExercise.zip](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/cc6ee08f-2e6f-4fe9-b8f4-98ba8d963c6b/NanoExercise.zip)

Download the above zip file.  Unzip it and then navigate to the resulting directory using the command line.

## Part 1

1. Open up the `recipe.txt` file using `nano`
2. On line 3, add your own name after `Author:` so that it says `Author: Stevie Wonder` or whatever your name is
3. Whoever wrote this recipe didn't know how to spell "parmesan", so instead they wrote "parm".  Please update the two instances of "Parm" to "Parmesan".  You can do this manually or by using nano's replace feature.
4. Write out your changes! Close the file.

## Part 2

1. Open up the `website.html` file with `nano`
2. This html file contains a simple website for a fictional restaurant called "Ristorante Colt".  You recently purchased the restaurant and have decided to change its name! Please replace all instance of "Ristorante Colt" with your new restaurant's name.  Do this using a nano shortcut, rather than manually replacing each one.
3. Save your changes and close the file!

## Part 3

1. The `country-data.json` file contains a large country dataset, with over 39,000 lines of json!
2. Unfortunately, there is a typo on line **15399**.  It says "Hondras" but it should say "Honduras".  Please fix this!  Rather than scrolling for a decade, use a nano shortcut to jump to line **15399**.
3. **Bonus:** Figure out how to tell `nano` to open the file at exactly **15399**. `nano +15399 ../mnt/e/Journey-To-Coding/Online-Project-Ideas/colt-steele/the-linux-command-line-b
ootcamp/Exercises/NanoExercise/country-data.json`

## Bonus

1. The `review.txt` file contains a text review of the Cacio E Pepe recipe from `recipe.txt`
2. Open up the `recipe.txt` file using `nano` and scroll to the bottom. 
3. Using a nano shortcut we have not covered, insert the contents of `review.txt` at the bottom of `recipe.txt`.
