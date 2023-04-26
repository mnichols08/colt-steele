# The Environment

The shell maintains a set of information during a shell session, known as `the environment`. It is just a series of key-value pairs that define properties like:
- Your home directory
- Your working directory
- The name of your shell
- The name of the logged in user

Viewing The Environment
Use the `printenv` command to view the environment variables and their current values. Because there are quite a few values, it can be useful to pipe the output to less.

Parameter Expansion
If we write out the name of the environment variable prefixed with a dollar sign ($), the shell will replace it with the actual value.
For example, echo $USER results in the USER variable's value

Defining Variables
To define a variable, use the syntax variable=value
Built-in variables are upper-cased, so it is a common convention to lowercase customer variables to prevent confusion.

Aliases
We can define our own commands using the alias keyword.
In the example below, we are defining an alias called ll which is equivalent to running ls -al. To execute it, we would simply run ll
`alias ll='ls -al'`

Startup Files
When we log in, the shell reads information from startup files. First, the shell reads from global config files that effect the environment for all users. Then, the shell reads startup files for specific users.
The specific files the shell reads from depends on the type of session: login vs. non-login shell sessions

For login sessions:
- `/etc/profile` - global config for all users
- `~/.bash_profile` - user's personal config file
- `~/.bash_login` - read if bash_profile isn't found
- `~/.profile` - used if previous two are not found

For non-login sessions (typical session when you launch the terminal via the GUI):
- `etc/bash.bashrc` - global config for all users
- `~/.bashrc` - specific settings for each user. This is where we can define our own settings and configuration.

I set my shell to be pretty using `PS1="\[\e[36m\]mnichols08>\[\e[m\]\[\e[35m\]\W\[\e[m\]\[\e[32m\]:\[\e[m\]\[\e[31m\]\d\[\e[m\]\[\e[32m\]@\[\e[m\]\[\e[33m\]\T\[\e[m\]\[\e[32m\]>\[\e[m\] "`