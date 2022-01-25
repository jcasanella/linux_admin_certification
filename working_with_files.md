# Working With Files

## Starting with vi

Vi has two different operating modes:

* Command
* Input

Always starts in command mode. 

### Adding Text

To switch to the input mode, enter any of the following letters and once you finish, click `Esc` key.

* `a`: Add command, you can input text to the right of the cursor
* `A`: Add end command, input text to the end of the line
* `i`: Insert command, input text to the left of the cursor
* `I`: Insert at beginning, input text at the beginning line
* `o`: Open below, input text below the line
* `O`: Open above command, opens a line above the current line

### Moving around

To move around the text:

* `Arrow keys`: We can use the arrow keys to move around the text. Another option is `h` (left), `l` (right), `j` (down), `k` (up) keys.
* `w`: Move cursor to the next word, delimited by spaces, tabs or punctuation
* `W`: Move cursor to the next word, delimited by spaces or tabs.
* `b`: Move cursor to the previous word, delimited by spaces, tabs or punctuation
* `B`: Move cursor to the previous word, delimited by spaces or tabs.
* `0 (zero)`: beginning of the current line
* `$`: end of the current line
* `H`: Move the cursor upper left corner of the screen
* `M`: Move the cursor to the middle of the screen, beginning of line
* `L`: Move the cursor lower left corner of the screen
* `Ctrl+f`: Page ahead one page at a time
* `Ctrl+b`: Page back one page at a time
* `G`: Goes to the last line
* `nG`: Goes to the n line 

### Deleting, copying and changing text

* `x`: Delete the character under the cursor
* `X`: Delete the character before the cursor
* `dw`: Delete a word after the current position
* `db`: Delete a word before the current position
* `dd`: Delete entire line
* `c$`: Change until the end of the line. Any we write, will replace until the end of the line. Command finishes when you click `Esc`
* `c0`: Changes from the previous character until beginning of line, anything that we write will be replaced. Command finishes when you click `Esc`
* `cl`: Erases (`c`) the current letter `l` and goes into input mode
* `cc`: Erases (`c`) the line `c` and goes into input mode
* `yy`: Copies the current line and put into the buffer

Some of these commands can be modified using numbers, see some examples:

* `3dd`: Deletes (`d`) three (`3`) lines (`d`) 
* `3dw`: Deletes (`d`) the (`3`) next words (`w`)
* `5cl`: Changes (`c`) the next five (`5`) letters (`l`) - replace
* `12j`: Moves 12 lines down (`j`)
* `5cw`: Erases (`c`) the next five words (`w`)

### Pasting text

Once the text is in the buffer, this can be pasted using `p` or `P`

* `P`: Puts the text to the left of the cursor, if the text contain letters or words. If contains lines, they're copied above

* `p`: Puts the text to the right of the cursor, if the text contain letters or words. If contains lines, they're copied below

### Exiting vi

* `:w` Saves the current content but you continue in vi
* `:wq` Saves the current content and exits from vi
* `:q` Exits from vi if there's no unsaved changes
* `:q!` Exits from vi without saving changes

### Searching for text

To search for a string you can use the characters `/` to search forward and `?` to search backward

* `/hello`: Searches forward for the hello string
* `?hello`: Searches backward for the hello string
* `/[Pp]rint`: Searches forward either for Print or print

After search use `n` or `N` to search again

## Finding files

