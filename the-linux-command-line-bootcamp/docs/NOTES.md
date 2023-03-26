# Notes

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

_One Small Piece of Advice_
```
DO NOT MEMORIZE
JUST PRACTICE
(We naturally memorize the commands that we use most often)
```

## The World of Operating Systems
Most operating systems can be grouped into two families: 
- The Microsoft NT descendents including Windows, XBOX, and Windows Phone/Mobile
- Pretty much every other OS with lineage dating back to UNIX, including MAX OS X, Linux, Android, Chrome OS, and even the PS4

[Operating Systems: Timeline and Family Tree](https://eylenburg.github.io/os_familytree.htm)
[Slideshow PDF](./assets/01_Linux_Introduction.pdf)

Within the majority of popular ones, we have Windows, or the others.
The reason that it matters is because the commands are meant to work within almost any UNIX environment but don't expect them to work on WINDOWS

### So what is UNIX?
Well [UNIX](https://unix.org/) is an Operating System developed at Bell Labs in the mid 60s. It is considered to to be the grandfather of many modern operating systems that we frequently use today.

### The UNIX Philosophy
Early OS were tightly knit with specific hardware. Unix decoupled the two and could be ported to other hardware
It emphasizes modular software design and the creation of small individual programs that can be combied to perform complex tasks.
- Write programs that do one thing and do it well.
- Write programs to work together.
- Write programs to handle text streams, beacause that is a universal interface.

### Distinction between True UNIX and UNIX-Like
UNIX is a trademark of global consortium called The Open Group. It is sort of a certification that an OS can apply for. It involves testing and compliancy and dues.
UNIX-Like is when a  Operating System meets many or even all of the standards required but are not official. They cannot legally use the UNIX name. Like Linux, for example.

[A history of UNIX](https://spectrum.ieee.org/the-strange-birth-and-long-life-of-unix)

### Exploring the Original UNIX Manual

```
cat
```
Hasn't really changed since it was created.
```
find
```
In the original manual - it is incredibly short.
But today -
It has grown to be a very very complicated command.

This goes to show that we are working with an evolving language.

## So where does LINUX come into play?

LINUX and all of the flavors of LINUX are not actually UNIX so they are are not actually a part of the official UNIX Group as previously mentioned.
Instead, there are a pioneer of the Free Software Movement, which is a movement that began in the 1990s to diversify software.
In 1984, Richard Stallman created GNU, which was a totally free and open source version of the software at this time
At the same time, another developer named Linus Torvalds, was developing a kernel, which was known as Linux. The two combined their projects to create LINUX as we know it - well in it's infancy.

[So what is it? GNU or Linux?](https://www.howtogeek.com/139287/the-great-debate-is-it-linux-or-gnulinux/)

It would definitly be annoying to be Richard Stallman in this situation
Linux is the kernel, GNU is the Shell and UI

# Shell -> OS
A shell is a computer interface to an operating system. They expose the OS's services to human users or other programs.

A Terminal is a program that runs a shell. Originally terminals were physical devices, but these days we work with software terminals.

The most commonly used one and the one we will be using is `bash` or born-again sh(ell); kind of like a shell 2.0 if you will?

Opening the terminal
Right click inside of any window and hit open with terminal
Or open a terminal

When a terminal is open, our open text to type into is called the `prompt`
This is where we can type to the computer directly

First offical command to learn is
`clear` - clears the terminal

What is we don't have a `prompt`?
What if the prompt says 
`>`?

Well, the terminal is confused because it is waiting for a quote to close.

Up next is the `date` command

It may not seem very useful, but it is where we are starting.
It is case sensitive on some terminals

But what about `date asdasd`?
Well that command is not found, but there are commands to learn but we will come back to that.

Next we have `ncal` or new calander

when trying to use this with bash I couldn't and by then I finally got Ubuntu installed but it also threw an error about not being able find and suggested installing but it threw this
```
apt install ncal
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
E: Unable to locate package ncal
```
to which I fixed with
```
apt update
```
as per a suggestion found googling

it now works
```
    March 2023
Su     5 12 19 26
Mo     6 13 20 27
Tu     7 14 21 28
We  1  8 15 22 29
Th  2  9 16 23 30
Fr  3 10 17 24 31
Sa  4 11 18 25
```

the next command to use is `cal` which does not do much differnet besides an old school style of a calander





