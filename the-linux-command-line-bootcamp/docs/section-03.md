# Command Basics

[PDF](./assets/02_Command_Basics.pdf)

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

we can use the arrows in the terminal to do various tasks... < and > will navigate the text cursor

and the ^ arrow will allow me to take a shortcut to skip to the previous command or the down arrow to move back one

The vast majority of commands follow a particular structure.
\>`command` -`options` `arguments`
\- the first thing typed into the prompt is the `command` and will tell the terminal what function to run
\- options are passed in by flagging them with a `-` before and `arguments` are passed in last and usually are things the command will act upon or use.

Arguments are parameters that we give to the command to work with or operate on. For example:

```
echo
```

will print and empty line
but

```
echo hello

```

will print a line

But some require arguments and others dont and this one we can pass in as many argumentsa s we want and it will just concatenate them together

```

echo check this long string out that has a lot of characters and spaces!

```

back to ncal though
We can specify a year or a month

```

ncal 1989

```

or even

```

ncal october 1989

```

The point is this command takes no arguments or works with multiple and will return calanders

There are some others, that do require arguments or will just `sort` of linger
hehe, `sort` for example
typing simply `sort` into the terminal prompt will cause a hangup

These commands need arguments and will wait for them before running. Press ctrl + c to exit if you get hung up by doing that.

`rm` is a command which will require an argument and complain if you dont, but this one will remove a file

__options__
Every command usually has a selection of options ehich we can use while executing the command. They will modify the behavior of the command in predefined ways. 
They are prefixed with a hyphen or dash as in `-` such as `command -option` or `sort -r colors.txt`

`ncal -h` to remove highlighting
`ncal -j` to get a calander with the number days in the year
`ncal -M` with Monday as the first day of week.
`ncal -3` with the surrounding months

## Combining options

Sometimes we might want to comine two or three different options together
Well we can just add additional options to the command such as
```
ncal -j -M -3
```

or, we can also write
```
ncal -jM3
```

## Long Form option
If we want to write more sensical scripts in UNIX, we can pass in a long-form option
We do that by supplying two hyphens instead of one `--`
```
date --universal
```
It is important to note if you intend a long-form option you must use the two hyphens or it will follow the previous logic and try to apply a `-a` as well as a `-t` and a `-e`

`-u` will return unique results
`-r` will return reversed results
of course you could also type
`--reverse`
or `--unique`
but `-ru` would work just as well to combine them

`ncal -A 5` for printing months After (and requires a number)
`ncal -B 5` for printing months Before (and requiresa number)

can also type
`ncal -A5 -B5` to combine

another neat trick is to type
`ncal october 1989 -B1 -A1 -M` to get one month before and after the month I was born and starting on mondays