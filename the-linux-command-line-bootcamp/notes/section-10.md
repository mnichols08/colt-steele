# 10 Redirection

## Standard Streams
	The three standard streams are **communication channels** between a computer program and its environment.
	They are:
	1. Standard Input
	- 
	2. Standard Output
	- Standard Output is a place to which a computer or command can send information. The information could go to a screen to be displayed, to a file, or even to a printer or other devices.
	- By default our terminal outputs directly to our terminal.
	- It is possible to change our output to something different such as saving to a file.
	3. Standard Error
	- By default any errors are displayed within the terminal.
	- It is possible to change where we output errors.
	
### Simple Redirection
	1. `<command> > <filename>` - Overwrites
	2. `<command> >> <filename>` - Appends
### Examples
	1. `echo meow > cat.txt` - create a new filename of cat.txt and pass in the string meow
	2. `echo meow >> cat.txt` - filename of cat.txt and append in the string meow

#### Inputs
	Some terminal applications, like cat, allow us to see standard input in action. We can do this by simply typing the word cat into the terminal and pressing enter.
	This allows us to instead of redirecting the cat command to a file, we can redirect a command into the cat command. At this point we haven't learned how this would help
	`sort < cal.txt` - same end result as `sort > cal.txt`. - provide via standard input the cal.txt file and then.
	`cat < cat.txt >> sounds.txt`- provide via standard input the cat.txt file `< sounds.txt` and append the output to the sounds.txt file

## Output
	By default the output will display to the terminal - without a redirect.
	`ls slkfdjslkj 2> errorlog.txt` - with a redirect we can create a new file when an error occurs
	`cat filethatdoesntexist.txt 2>> errorlog.txt` appends any errors that occur
	`cat dog.txt cat.txt > animals 2>> errorlog.txt` - run the cat command on dog.txt and cat.txt and change the contents of the file called animals and append any errors to the errorlog.txt file
	`ls docs &> output.txt` or `ls docs &>> output.txt` allows us to take both the standard output and error and redirect them into a file	

# Redirection Exercise

Download the files for this exercise:

[Wildlife.zip](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5347afb9-a379-4ccc-a6a7-25da129f3ad0/Wildlife.zip)

Unzip the `Wildlife` folder and navigate to it via the command line. [x]

## Your Task

You are taking part in a wildlife survey in a remote portion of the Peruvian Amazon! This morning, three of your research assistants each went on transect walks where they recorded the individual species they observed.     Your (simple) job is to combine their findings into a new file that contains all the species that were observed!

1. Create a new file called `all-species.txt` that contains the combined contents of `angela-survey.txt`, `nico-survey.txt`, and `juan-survey.txt`.  Do this using a single command! [x]
2. The problem with the `all-species.txt` file is that it contains duplicate entries!  Use a single command to sort the lines in alphabetical order, only sorting uniques, and send the output to a new file called `sorted-animals.txt` [x]
3. Now, you go out for a nice morning stroll and stumble upon a large anaconda sunning itself on a log.  You should add this observation to the list of species!! [x]
    1. Start by appending the current date to the end of the `sorted-animals.txt` file using a command (don't open the file manually!) [x]
    2. Then append the text "Green Anaconda" to the end of `sorted-animals.txt`[x]
4. Run the non-existent command `ughhh` and redirect any error messages so that they are **appended** to the sorted-animals.txt file. [x]
