# How to get Help

Major part of commands we can use `--help`

```
ls --help                                                                                                                                                                                           ✔  5332  07:51:10
Usage: ls [OPTION]... [FILE]...
List information about the FILEs (the current directory by default).
Sort entries alphabetically if none of -cftuvSUX nor --sort is specified.

Mandatory arguments to long options are mandatory for short options too.
  -a, --all                  do not ignore entries starting with .
  -A, --almost-all           do not list implied . and ..
      --author               with -l, print the author of each file
  -b, --escape               print C-style escapes for nongraphic characters
      --block-size=SIZE      scale sizes by SIZE before printing them; e.g.,
                               '--block-size=M' prints sizes in units of
                               1,048,576 bytes; see SIZE format below
  -B, --ignore-backups       do not list implied entries ending with ~
  -c                         with -lt: sort by, and show, ctime (time of last
                               modification of file status information);
                               with -l: show ctime and sort by name;
                               otherwise: sort by ctime, newest first
  -C                         list entries by columns
      --color[=WHEN]         colorize the output; WHEN can be 'always' (default
                               if omitted), 'auto', or 'never'; more info below
  -d, --directory            list directories themselves, not their contents
  ...
  ```

  We can access to the manual using the command `man`

  ```
  man journalctl

  JOURNALCTL(1)                                                                                                                 journalctl                                                                                                                JOURNALCTL(1)

NAME
       journalctl - Query the systemd journal

SYNOPSIS
       journalctl [OPTIONS...] [MATCHES...]

DESCRIPTION
       journalctl may be used to query the contents of the systemd(1) journal as written by systemd-journald.service(8).

       If called without parameters, it will show the full contents of the journal, starting with the oldest entry collected.

       If one or more match arguments are passed, the output is filtered accordingly. A match is in the format "FIELD=VALUE", e.g.  "_SYSTEMD_UNIT=httpd.service", referring to the components of a structured journal entry. See systemd.journal-fields(7) for a
       list of well-known fields. If multiple matches are specified matching different fields, the log entries are filtered by both, i.e. the resulting output will show only entries matching all the specified matches of this kind. If two matches apply to the
       same field, then they are automatically matched as alternatives, i.e. the resulting output will show entries matching any of the specified matches for the same field. Finally, the character "+" may appear as a separate word between other terms on the
       command line. This causes all matches before and after to be combined in a disjunction (i.e. logical OR).

       It is also possible to filter the entries by specifying an absolute file path as an argument. The file path may be a file or a symbolic link and the file must exist at the time of the query. If a file path refers to an executable binary, an "_EXE=" match
       for the canonicalized binary path is added to the query. If a file path refers to an executable script, a "_COMM=" match for the script name is added to the query. If a file path refers to a device node, "_KERNEL_DEVICE=" matches for the kernel name of
       the device and for each of its ancestor devices is added to the query. Symbolic links are dereferenced, kernel names are synthesized, and parent devices are identified from the environment at the time of the query. In general, a device node is the best
       proxy for an actual device, as log entries do not usually contain fields that identify an actual device. For the resulting log entries to be correct for the actual device, the relevant parts of the environment at the time the entry was logged, in
       particular the actual device corresponding to the device node, must have been the same as those at the time of the query. Because device nodes generally change their corresponding devices across reboots, specifying a device node path causes the resulting
       entries to be restricted to those from the current boot.

...
```

As you can see, man is really big, to understand better the different sections of the manual, running `man man` will see a description of the different sections that is make up the page.

```
MAN(1)                                                                                                                    Manual pager utils                                                                                                                   MAN(1)

NAME
       man - an interface to the on-line reference manuals

SYNOPSIS
       man  [-C  file] [-d] [-D] [--warnings[=warnings]] [-R encoding] [-L locale] [-m system[,...]] [-M path] [-S list] [-e extension] [-i|-I] [--regex|--wildcard] [--names-only] [-a] [-u] [--no-subpages] [-P pager] [-r prompt] [-7] [-E encoding] [--no-hyphen‐
       ation] [--no-justification] [-p string] [-t] [-T[device]] [-H[browser]] [-X[dpi]] [-Z] [[section] page[.section] ...] ...
       man -k [apropos options] regexp ...
       man -K [-w|-W] [-S list] [-i|-I] [--regex] [section] term ...
       man -f [whatis options] page ...
       man -l [-C file] [-d] [-D] [--warnings[=warnings]] [-R encoding] [-L locale] [-P pager] [-r prompt] [-7] [-E encoding] [-p string] [-t] [-T[device]] [-H[browser]] [-X[dpi]] [-Z] file ...
       man -w|-W [-C file] [-d] [-D] page ...
       man -c [-C file] [-d] [-D] page ...
       man [-?V]

DESCRIPTION
       man is the system's manual pager.  Each page argument given to man is normally the name of a program, utility or function.  The manual page associated with each of these arguments is then found and displayed.  A section, if provided, will direct  man  to
       look  only  in  that  section of the manual.  The default action is to search in all of the available sections following a pre-defined order ("1 n l 8 3 2 3posix 3pm 3perl 3am 5 4 9 6 7" by default, unless overridden by the SECTION directive in /etc/man‐
       path.config), and to show only the first page found, even if page exists in several sections.

       The table below shows the section numbers of the manual followed by the types of pages they contain.

       1   Executable programs or shell commands
       2   System calls (functions provided by the kernel)
       3   Library calls (functions within program libraries)
       4   Special files (usually found in /dev)
       5   File formats and conventions eg /etc/passwd
       6   Games
       7   Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7)
       8   System administration commands (usually only for root)
       9   Kernel routines [Non standard]
...
```

If we dont know the command to run, with the `apropos keyword` will show us all the man pages that have the keyword. If the command does not work, most likely we need to update the db, running `sudo mandb`
