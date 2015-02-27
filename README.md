# Learn vi editor for Unix

I will note what I learned using vi editor

## Starting vi and opening files

Open your **Terminal** app & type `vi filename`

## Operating Modes

There are two modes in **vi**, `command mode` & `Insert mode`.

### Command mode

In this mode commands are used to **move** around and edit text objects

<kbd>ESC</kbd> key returns you to `command mode`.

### Insert mode

This is the mode you use to type **insert** text into a buffer.

| Key | Description |
| ------ | ----------- |
| <kbd>i</kbd> | insert text **before** the cursor & <kbd>I</kbd> at the **start** |
| <kbd>a</kbd> | insert text **after** the cursor & <kbd>A</kbd> at the **end** |
| <kbd>o</kbd> | open a **new line below** the current line & <kbd>O</kbd> **above** |

### Saving files and exiting vi

**Saving changes**

GO to `command mode` and <kbd>ESC</kbd> then type `:wq`.

**Without saving changes**

   `:q!`

**Saving to another file**

   `:w filename`

### Viewing a file

   `view filename`

### Setting a wrap margin

   `set wm=5`

In insert mode, text is wrapped five (5) characters from the right margin of the screen.


