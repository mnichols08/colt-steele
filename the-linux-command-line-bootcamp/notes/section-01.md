# Section 01 - Orientation

Why Master The Command Line?
- It gives you far greater control over your computer
With a User Interface, we can drag and drop to achieve simple tasks, sure.
- The command line allows us to do things programatically like do certain things 

There is a random command we can type to print the programs using the most memory on your LINUX or MAC Computer
```
lsof / | awk '{ if($7 > 1048576) print $7/1048576 "MB" " " $9 " " $1 }' | sort -n -u | tail
```

Once you remember the basic commands - it becomes faster to just type in the terminal.
- A lot of times we can do multiple things in one line with the terminal.

**Automation**
If we wanted to have a new nested folder for every day of the year, we could manually do it with the GUI
- Or, we could type `mkdir Day{1..365}` into the terminal and it could be done for us [../Days](../Days)

You can bet your ass that the job you are applying for will want this to be a skillset of yours. (add it to your resume, dummy!)
It is absolutely necessary for cloud computing, deploying apps, etc.

The highest paying jobs out there love linux command line users
- So yeah, It is basically a requirement to have at least 50% of the commands but if you can master the command line you can make some serious $$

_One Small Piece of Advice From Colt_
```
DO NOT MEMORIZE
JUST PRACTICE
(We naturally memorize the commands that we use most often)
```