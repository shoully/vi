# Learn vi editor for Unix

I will note what I learned using vi editor, so it's `vi cheatsheet` or `vi for designers` :)

**Starting vi and opening files**

Open your **Terminal** app & type `vi filename`

* 1. Operating Modes

There are two modes in **vi**, `command mode` & `Insert mode`

* 2. Command mode

In this mode commands are used to **move** around and edit text objects

| Key | Description |
| ------ | ----------- |
| <kbd>ESC</kbd> | returns you to `command mode` |

**Insert mode**

This is the mode you use to type or **insert** text into a buffer

| Key | Description | Reverse | Description |
| ------ | ----------- | ----------- | ----------- |
| <kbd>i</kbd> | insert text **before** the cursor. | <kbd>I</kbd> | insert text at the **start** of the line. |
| <kbd>a</kbd> | insert text **after** the cursor. | <kbd>A</kbd> | insert text at the **end** of the line. |
| <kbd>o</kbd> | new line **below** the current line. | <kbd>O</kbd> | new line **above** the current line. |

**Saving files**

* Saving changes

Go to `command mode` by <kbd>ESC</kbd> then type the commant `:wq`

| Command | Description |
| ------ | ----------- |
| `:wq` or `ZZ` | Save the contents & quit vi |

* Without saving changes

Go to `command mode` by <kbd>ESC</kbd> then type the commant `:wq`   

| Command | Description |
| ------ | ----------- |
| `:q!` | Quit vi without saveing |

* Saving to another file

Go to `command mode` by <kbd>ESC</kbd> then type the commant `:w filename` while the `filename` is your file name

| Command | Description |
| ------ | ----------- |
| `:w filename` | Save the contents to the `filename` & quit vi |

**Viewing a file**

You can look at a file without the risk of altering its contents by using vi in "read only" mode.

| Command | Description |
| ------ | ----------- |
| `view filename` | Look at a file in "read only" mode |

**Redo and Undo**

Useful commants to undo, redo or repeat

| Command | Description |
| ------ | ----------- |
| `u` | undo changes |
| `:u` | undo one change |
| <kbd>CTRL</kbd>+<kbd>R</kbd> | redo change |
| `.` | repeat last change |

**Cut and paste**

Yank (copy) word or a line and paste it

| Command | Description |
| ------ | ----------- |
| `yy` | yank a line |
| `yw` | yank word |
| `y$` | yank to end of line |
| `p` | paste after cursor |
| `dd` | delete (cut) a line |
| `dw` | delete (cut) word |
| `d$` or `D` | delete to the end of the line |

**Search and replace**

Syntax:
       `:[address]s/old_text/new_text/`

| Address | Description |
| ------ | ----------- |
| `.` | current line |
| `n` | line number n |
| `.+m` | current line plus m lines |
| `%` | entire file |

**Setting a wrap margin**

| Command | Description |
| ------ | ----------- |
| `set wm=5` | Wrapp text five (5) characters |

In insert mode, text is wrapped five (5) characters from the right margin of the screen

**Contributing**

Pull requests and issues are welcome.
