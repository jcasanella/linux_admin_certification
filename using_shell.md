## Using the shell prompt

The default prompt for a regular user is simply a dollar sign: ```$```
The default prompt for the root user is a pound sign (also called a number sign or a hash tag): ```#```

In most Linux systems, the `$` and `#` prompts are preceded by your username, system name, and current directory name. 
For example, a login prompt for the user named `jake` on a computer named pine with `/usr/share/` as the current working directory would 
appear as follows:

```
[jake@pine share]$
```

## Choosing Your Shell

In most Linux systems, your default shell is the bash shell. To find out what is your default login shell, enter the following commands:
```
$ whoami
chris     pts/0      2019-10-21 22:45 (:0.0)
$ grep chris /etc/passwd
chris:x:13597:13597:Chris Negus:/home/chris:/bin/bash
```

When you log in to a Linux system, Linux views you as having a particular identity, which includes your username, group name, user ID, 
and group ID. Linux also keeps track of your login session: It knows when you logged in, how long you have been idle, and where you logged 
in from.

To find out information about your identity, use the id command as follows:
```
$ id
uid=1000(chris) gid=1000(chris) groups=1005(sales), 7(lp)
```

In this example, the username is chris, which is represented by the numeric user ID (**uid**) 1000. The primary group for chris also is called 
chris, which has a group ID (**gid**) of 1000. The user chris also belongs to other groups called sales (**gid 1005**) and lp (**gid 7**). These names and numbers represent 
the permissions that chris has to access computer resources.

You can see information about your current login session by using the `who` command. In the following example, the `-u` option says to add 
information about idle time and the process ID and `-H` asks that a header be printed:
```
$ who -uH
NAME    LINE   TIME          IDLE   PID   COMMENT
chris   tty1   Jan 13 20:57  .      2019
```

The output from this who command shows that the user chris is logged in on tty1 and his login session began at 20:57 on January 13. The IDLE time shows how long the shell has been open without any command being typed 
(the dot indicates that it is currently active). PID shows the process ID of the user's login shell. COMMENT would show the name of the remote computer 
from which the user had logged in, if that user had logged in from another computer on the network, or the name of the local X display if that user 
were using a Terminal window (such as :0.0).

## Locating Commands

Most user commands that come with Linux are stored in the `/bin, /usr/bin`, or `/usr/local/bin` directory. The `/sbin` and `/usr/sbin` directories contain administrative commands.

Here is the order in which the shell checks for the commands you type:

1. **Aliases**. These are names set by the alias command that represent a particular command and a set of options. 
2. **Shell reserved word**. These are words reserved by the shell for special use
3. **Function**. This is a set of commands that is executed together within the current shell.
4. **Built-in command**. This is a command built into the shell. Example: ls, cp, mv
5. **Filesystem command**. This command is stored in and executed from the computer's filesystem.

To determine the location of a particular command, you can use the `type` command. For example, to find out where the `bash` shell command is located, enter the following:
```
$ type bash
bash is /bin/bash
```
If a command resides in several locations, you can add the `-a` option to have all of the known locations of the command printed.

If a command is not in your PATH variable, you can use the `locate` command to try to find it. Using locate, you can search any part of the system that is accessible to you.

```
$ locate chage
/usr/bin/chage
/usr/sbin/lchage
/usr/share/man/fr/man1/chage.1.gz
/usr/share/man/it/man1/chage.1.gz
/usr/share/man/ja/man1/chage.1.gz
/usr/share/man/man1/chage.1.gz
/usr/share/man/man1/lchage.1.gz
/usr/share/man/pl/man1/chage.1.gz
/usr/share/man/ru/man1/chage.1.gz
/usr/share/man/sv/man1/chage.1.gz
/usr/share/man/tr/man1/chage.1.gz
```

If `locate` does not find files recently added to your system, run `updatedb` as root to update the locate database.

## Command History

The shell history is a list of the commands that you have entered before. Using the `history` command in a bash shell, you can view your previous commands.

Keystrokes for Navigating Command Lines

| Keystroke | Full Name | Meaning |
|---|---|---|
| Ctrl F | Character Forward | Go forward one character |
| Ctrl B | Character Backward | Go backward one character |
| Alt F | Word Forward | Go forward one word |
| Alt B | Word Backward | Go backward one word |
| Ctrl A | Beginning of Line | Go to the beginning of the current line |
| Ctrl E | End of Line | Go to the end of the current line |
| Ctrl L | Clear Screen | Clear Screen and leave line  at the top of the screen |
| Ctrl K | Cut end of line | Cut text to the end of the line |
| Ctrl U | Cut beginning of line | Cut text to the beginning of the line |
| Ctrl W | Cut previous word | Cut the word located behind the cursor |
| Alt D | Cut next word | Cut the word following the cursor |
| Ctrl C | Delete whole line | Delete the entire line |