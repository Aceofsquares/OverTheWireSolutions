# Bandit Level Solutions

Here, I will give a bit more in depth look at the solutions to the Bandit
problems.  I will try my best to explain why I did what I did as well as
the explanation for any code or commands.

Okay let's begin.

## Level 0 

Level 0 is just an explanation of how to connect to the games. 
The instructions are

> "The goal of this level is for you to log into the game using SSH. 
> The host to which you need to connect is bandit.labs.overthewire.org, 
> on port 2220. The username is bandit0 and the password is bandit0. 
> Once logged in, go to the Level 1 page to find out how to beat Level 1.

> *Commands you may need to solve this level*

> `ssh`"

So the information we have is that the server we want to connect to is 
bandit.labs.overthewire.org and the port is 2220.  We have to use SSH to
connect so run the following command

`
man ssh
`

The *man* command is short for manual and will display paged information
about a particular command.  You can use _space_ or _down arrow_ to move
 down the paged information and _b_ or _up arrow_ to move up the paged
 information.  To leave the manual press _q_.

To login, I use the format *username@server*.  The default port for the
ssh command is port 22 but to connect to a specific port we will use 
*-p port* according to the man pages. 

So, to complete level0 the complete command is

`ssh bandit0@bandit.labs.overthewire.org -p 2220`

You should connect and see see a password request.  According to the
instructions, *bandit0* is the password for the level0.

Congrats!  You've started down an addictive path to a game that teaches
you valuable skills.

## Level 0 -> Level 1

*GOAL*

> "The password for the next level is stored in a file called readme 
> located in the home directory. Use this password to log into bandit1 
> using SSH. Whenever you find a password for a level, use SSH (on port 
> 2220) to log into that level and continue the game."

> *Commands you may need to solve this level*

> `ls, cd, cat, file, du, find`

To go from level 0 to level 1 we need to login as bandit0 and locate the
password for bandit1.  This is how these challenges are set up.  You login
to bandit(X) to find the password for bandit(X+1).

Using what we've learned in just level 0, login to bandit 0.  

`ssh bandit0@bandit.labs.overthewire.org -p 2220`

Give the password, *bandit0*, and we're in.  Now, the description states
that the password to the next level is in a file called *readme* located
in the home directory.  The home directory is usually located in
*/home/(username)*.  So for bandit0, the home directory is located in
*/home/bandit0*.  To see where we landed in the file system, let's use 
`pwd`.  Type that in and press enter and you should see */home/bandit0*.
I know that command wasn't listed in the commands we may need but it's 
nice to know.  `pwd` gives us our location in the filesystem.  We are in
our home directory so let's list the files and directories using one of
the commands above.  You should `man command`, replacing command with a
one of the listed commands to get a description of what you should use
(and to learn what the commands do).

Did you spot what we needed?  We should use the `ls` command.  When you
press enter you will see a list of files and directories (in this case,
only one).  The file *readme* is at our location so now we need to read 
it.  Did you `man command` the other commands?

To read the file we can use the `cat` command.  Type

`
cat readme
`

You will now have a string of text which is the password for bandit1.

Being able to navigate, open, and know where you are in the file system
should almost be second nature so practice, read, and play with the 
ls, cd, cat commands and any others you find along the way. (Some will
be used later on).

Once you are done with the session, type `exit`.

