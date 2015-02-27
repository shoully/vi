# Learn vi editor for Unix

I will note what I learned using vi editor

## Operating Modes

There are two modes in **vi**, `command mode` & `Insert mode`.

### Command mode

In this mode commands are used to **move** around and edit text objects

Pressing the <kbd>ESC</kbd> key returns you to `command mode`.

### Insert mode

This is the mode you use to type **insert** text into a buffer. There are several commands that you can use to enter this mode.

| Key | Description |
| ------ | ----------- |
| <kbd>i</kbd> | insert text **before** the cursor & <kbd>I</kbd> at the `start` |
| <kbd>a</kbd> | insert text **after** the cursor & <kbd>A</kbd> at the `end` |
| <kbd>o</kbd> | open a **new line below** the current line & <kbd>O</kbd> `above`|

### Save the file

<kbd>ESC</kbd> then type `:wq` will save and exit.
