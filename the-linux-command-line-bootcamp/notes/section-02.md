## Section 02 - The World of Operating Systems
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