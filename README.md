# vi

I will note what I learned using vi editor

## Operating Modes

There are two modes in `vi`.

### Command mode

In this mode commands are used to `move` around and edit text objects

Pressing the <kbd>ESC</kbd> key returns you to `command mode`.

### Insert mode

This is the mode you use to type `insert` text into a buffer. There are several commands that you can use to enter this mode.

Pressing <kbd>i</kbd> will `insert` text `before` the cursor, & <kdb>I</kbd> at the `start` of the current line.

Pressing <kbd>a</kbd> will insert text `after` the cursor, & <kdb>A</kbd> at the `end` of the current line.

Pressing <kbd>o</kbd> will open a `new line below` the current line, & <kdb>O</kbd> will open a new line `above`.

### save the file

<kbd>ESC</kbd> then type `:wq` will save and exit.
