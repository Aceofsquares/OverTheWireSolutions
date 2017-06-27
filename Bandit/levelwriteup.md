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
> Once logged in, go to the Level 1 page to find out how to beat Level 1."

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
