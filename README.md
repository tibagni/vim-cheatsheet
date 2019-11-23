# vim-cheatsheet

## General
```
:help keyword # open help for keyword
:w            # write the buffer to the file (save)
:w file       # write buffer to specified file (save)
:o file       # open file
:q!           # quit the current window (force)
:wq           # write and quit
:qa           # quit all open tabs
:qa!          # quit all open tabs (force)
:wqa          # write and quit all open tabs
```

## Cursor movement
```
h        # move cursor left (left arrow)
j        # move cursor down (down arrow)
k        # move cursor up (up arrow)
l        # move cursor right (right arrow)
H        # move to top of screen
M        # move to middle of screen
L        # move to bottom of screen
w        # jump forwards to the start of a word
W        # jump forwards to the start of a word (words can contain punctuation)
e        # jump forwards to the end of a word
E        # jump forwards to the end of a word (words can contain punctuation)
b        # jump backwards to the start of a word
B        # jump backwards to the start of a word (words can contain punctuation)
0        # jump to the start of the line
^        # jump to the first non-blank character of the line
0w       # jump to the begining of the first word of indented lines
$        # jump to the end of the line
g_       # jump to the last non-blank character of the line
gg       # go to the first line of the document
G        # go to the last line of the document
5G       # go to line 5
fx       # jump to next occurrence of character x
tx       # jump to before next occurrence of character x
}        # jump to next paragraph (or function/block, when editing code)
{        # jump to previous paragraph (or function/block, when editing code)
zz       # center cursor on screen
Ctrl + f # move forward one full screen
Ctrl + b # move back one full screen
Ctrl + d # move forward 1/2 a screen
Ctrl + u # move back 1/2 a screen
```

## Additional movement (motion) (to use in conjunction with comands)
```
iw      # inner word - applies the command to the word the cursor is on
is      # inner sentence - applies the command to the sentence the cursor is on
i"      # inner quotes - applies the command to the text inside the quotes
i[      # inner [] - applies the command to the text inside the [] the cursor is on
i{      # inner {} - applies the command to the text inside the {} the cursor is on
i(      # inner () - applies the command to the text inside the () the cursor is on
i<      # inner <> - applies the command to the text inside the <> the cursor is on
it      # inner tag - applies the command to the text inside the tags the cursor is on <tag>...</tag>

aw      # a word - same as iw
as      # a sentence - same as is
a"      # a quotes - same as i" including the quites
a[      # a [] - same as i[ including the []
a{      # a {} - same as i{ including the {}
a(      # a () - same as i( including the ()
a<      # a <> - same as i< including the <>
at      # a tag - same as it including the tags
```

## Insert mode - inserting/appending text
```
i        # insert before the cursor
I        # insert at the beginning of the line
a        # insert (append) after the cursor
A        # insert (append) at the end of the line
o        # append (open) a new line below the current line
O        # append (open) a new line above the current line
Esc      # exit insert mode
```

## Editing
```
r         # replace a single character
J         # join line below to the current one
cc        # change (replace) an entire line
c[motion] # change (replace) from the cursor to the move-to point.
dd        # delete an entire line
d[motion] # delete from the cursor to the move-to point.
s         # delete character and substitute text
S         # delete line and substitute text (same as cc)
xp        # transpose two letters (delete and paste)
.         # repeat last command
u         # undo
Ctrl + r  # redo
```

## Marking text (visual mode)
```
v        # start visual mode, mark lines, then do a command (like y-yank)
V        # start visual mode marking entire line
Ctrl + v # start visual block mode
o        # move to other end of marked area
O        # move to other corner of block
Esc      # exit visual mode
```

## Visual commands
```
y       # yank (copy) marked text
d       # delete marked text
c       # delete the marked text and go into insert mode (like c does above)
```

## Cut and paste
```
yy        # yank (copy) a line
y[motion] # yank (copy) from the cursor to the move-to point.
p         # put (paste) the clipboard after cursor
P         # put (paste) before cursor
dd        # delete (cut) a line
d[motion] # delete (cut) from the cursor to the move-to point.
D         # delete (cut) to the end of the line (same as d$)
x         # delete (cut) character
```

## Search and replace
```
/pattern       # search for pattern
?pattern       # search backward for pattern
\vpattern      # 'very magic' pattern: non-alphanumeric characters are interpreted as special regex symbols (no escaping needed)
n              # repeat search in same direction
N              # repeat search in opposite direction
:%s/old/new/g  # replace all old with new throughout file
:%s/old/new/gc # replace all old with new throughout file with confirmations
```

## Search in multiple files
```
:vimgrep /pattern/ {file} # search for pattern in multiple files
:cn                       # jump to the next match
:cp                       # jump to the previous match
:copen                    # open a window containing the list of matches
```

## Working with multiple files
```
:e file       # edit a file in a new buffer
:bnext or :bn # go to the next buffer
:bprev or :bp # go to the previous buffer
:bd           # delete a buffer (close a file)
:ls           # list all open buffers
```

## Tabs
```
:tabnew or :tabnew file # open a file in a new tab
:tabe                   # same as tabnew
Ctrl + wT               # move the current split window into its own tab
gt or :tabnext or :tabn # move to the next tab
gT or :tabprev or :tabp # move to the previous tab
<number>gt              # move to tab <number>
:tabmove <number>       # move current tab to the <number>th position (indexed from 0)
:tabclose or :tabc      # close the current tab and all its windows
:tabonly or :tabo       # close all tabs except for the current one
:tabdo command          # run the command on all tabs (e.g. :tabdo q - closes all opened tabs)
```

## Windows
```
:sp file      # open a file in a new buffer and split window
:vsp file     # open a file in a new buffer and vertically split window
Ctrl + ws     # split window
Ctrl + ww     # switch windows
Ctrl + wq     # quit a window
Ctrl + wv     # split window vertically
Ctrl + wh     # move cursor to the left window (vertical split)
Ctrl + wl     # move cursor to the right window (vertical split)
Ctrl + wj     # move cursor to the window below (horizontal split)
Ctrl + wk     # move cursor to the window above (horizontal split)
```
