# Learn vi/Vim Editor for Unix (and beyond!)

Welcome to this enhanced guide for mastering the `vi` and `Vim` text editors! While `vi` is a powerful classic, `Vim` (Vi IMproved) builds upon it with a wealth of features that make it an indispensable tool for developers and power users. This guide will cover the fundamentals of `vi` and introduce you to many of `Vim`'s powerful capabilities.

**Goal**: To provide a comprehensive cheatsheet and learning resource for navigating, editing, and manipulating text efficiently using `vi`/`Vim`.

## Getting Started

To open or create a file with `vi` or `vim`:

```bash
vim filename   # Recommended: use vim for improved features
vi filename    # Classic vi
```

## Operating Modes

`vi`/`Vim` operates on the principle of modal editing, offering distinct modes for different tasks. This efficiency is a core strength once mastered.

### 1. Normal (Command) Mode

This is the default mode when you open `vi`/`Vim`. In this mode, keys are interpreted as commands to navigate, delete, copy, paste, and manipulate text objects. You **do not** type text directly here.

| Key | Description |
| :------ | :----------- |
| <kbd>ESC</kbd> | Returns you to `Normal mode` from any other mode. Crucial for resetting your state. |
| <kbd>Ctrl</kbd>+<kbd>[</kbd> | Alternative to <kbd>ESC</kbd> (especially useful for touch typists). |

### 2. Insert Mode

This is the mode where you type or insert text into the buffer. All characters you type are entered into the file.

| Key | Description | Reverse/Alternative | Description |
| :------ | :----------- | :----------- | :----------- |
| <kbd>i</kbd> | Insert text **before** the cursor. | <kbd>I</kbd> | Insert text at the **start** of the current line. |
| <kbd>a</kbd> | Insert text **after** the cursor. | <kbd>A</kbd> | Insert text at the **end** of the current line. |
| <kbd>o</kbd> | Open a new line **below** the current line and enter Insert mode. | <kbd>O</kbd> | Open a new line **above** the current line and enter Insert mode. |
| <kbd>s</kbd> | Delete character under cursor and enter Insert mode. | <kbd>S</kbd> | Delete current line and enter Insert mode. |

### 3. Visual Mode (Vim only)

Allows you to select blocks of text using the cursor keys, similar to selecting text with a mouse. Once text is selected, you can apply Normal mode commands to the selection (e.g., delete, yank, change).

| Key | Description |
| :------ | :----------- |
| <kbd>v</kbd> | Enter **character-wise** Visual mode. |
| <kbd>V</kbd> | Enter **line-wise** Visual mode. |
| <kbd>Ctrl</kbd>+<kbd>v</kbd> | Enter **block-wise** Visual mode (for rectangular selections). |

### 4. Command-Line Mode (Ex Mode)

Accessed by typing `:` from Normal mode. This mode allows you to execute powerful commands, often affecting multiple lines or the entire file, like saving, quitting, search/replace, and file operations.

## Basic Navigation (Normal Mode)

Moving around efficiently is key to `vi`/`Vim` mastery.

| Key | Description | Key | Description |
| :------ | :----------- | :------ | :----------- |
| <kbd>h</kbd> | Move cursor **left**. | <kbd>l</kbd> | Move cursor **right**. |
| <kbd>j</kbd> | Move cursor **down**. | <kbd>k</kbd> | Move cursor **up**. |
| <kbd>w</kbd> | Move to the start of the **next word**. | <kbd>b</kbd> | Move to the start of the **previous word**. |
| <kbd>e</kbd> | Move to the **end** of the current word. | <kbd>0</kbd> (zero) | Move to the **start** of the line. |
| <kbd>$</kbd> | Move to the **end** of the line. | <kbd>^</kbd> | Move to the first **non-blank character** of the line. |
| <kbd>gg</kbd> | Go to the **first line** of the file. | <kbd>G</kbd> | Go to the **last line** of the file. |
| <kbd>5gg</kbd> or <kbd>5G</kbd> | Go to **line 5**. | <kbd>H</kbd> | Move to the **top** of the screen. |
| <kbd>M</kbd> | Move to the **middle** of the screen. | <kbd>L</kbd> | Move to the **bottom** of the screen. |
| <kbd>Ctrl</kbd>+<kbd>f</kbd> | Scroll **forward** one screen. | <kbd>Ctrl</kbd>+<kbd>b</kbd> | Scroll **backward** one screen. |
| <kbd>Ctrl</kbd>+<kbd>d</kbd> | Scroll **down** half a screen. | <kbd>Ctrl</kbd>+<kbd>u</kbd> | Scroll **up** half a screen. |

## Saving & Quitting (Command-Line Mode)

Always return to `Normal mode` (<kbd>ESC</kbd>) before typing `:` commands.

| Command | Description |
| :------ | :----------- |
| `:w` | Save the file without quitting. |
| `:q` | Quit the editor (only if no changes have been made). |
| `:wq` or <kbd>ZZ</kbd> | Save changes and quit. |
| `:x` or <kbd>ZQ</kbd> | Same as `:wq`, but only writes if changes were made. |
| `:q!` | Quit without saving changes (force quit). |
| `:w filename` | Save the current buffer's contents to `filename`. |
| `:saveas filename` | Save the current buffer to a new file named `filename`. |
| `:qa!` | Quit all open buffers without saving (force all). |

## Undo, Redo & Repeat (Normal Mode)

Essential for correcting mistakes and streamlining repetitive actions.

| Command | Description |
| :------ | :----------- |
| <kbd>u</kbd> | Undo the last change. |
| <kbd>Ctrl</kbd>+<kbd>r</kbd> | Redo the last undone change. |
| <kbd>.</kbd> | Repeat the last change (very powerful!). |

## Deleting, Copying & Pasting (Normal Mode)

These commands often combine with **motions** (like `w` for word, `$` for end of line) to specify what to act upon.

| Command | Description | Example |
| :------ | :----------- | :----------- |
| `d` | Delete (cut) text. | `dw` (delete word), `d$` (delete to end of line), `dd` (delete current line), `dG` (delete to end of file). |
| `y` | Yank (copy) text. | `yw` (yank word), `y$` (yank to end of line), `yy` (yank current line), `yG` (yank to end of file). |
| `p` | Paste **after** the cursor (or below the current line for whole lines). | |
| `P` | Paste **before** the cursor (or above the current line for whole lines). | |
| `x` | Delete character under cursor. | |
| `X` | Delete character before cursor. | |

**Using Counts**: Prefix commands with a number to repeat them.
*   `5dd`: Delete 5 lines.
*   `3yw`: Yank 3 words.

## Search and Replace (Command-Line Mode)

`vi`/`Vim` provides powerful search and replace capabilities using regular expressions.

| Command | Description |
| :------ | :----------- |
| `/pattern` | Search forward for `pattern`. |
| `?pattern` | Search backward for `pattern`. |
| <kbd>n</kbd> | Repeat the last search in the same direction. |
| <kbd>N</kbd> | Repeat the last search in the opposite direction. |
| `:s/old/new/` | Replace the first occurrence of `old` with `new` on the current line. |
| `:s/old/new/g` | Replace **all** occurrences of `old` with `new` on the current line (`g` for global). |
| `:%s/old/new/g` | Replace all occurrences of `old` with `new` throughout the **entire file**. |
| `:%s/old/new/gc` | Replace all occurrences, but **confirm** each replacement with `c` (confirm). |
| `:n,ms/old/new/g` | Replace `old` with `new` globally between line `n` and line `m`. |

**Address Explanations:**

| Address | Description |
| :------ | :----------- |
| `.` | Current line. |
| `n` | Line number `n`. |
| `.+m` | Current line plus `m` lines. |
| `$` | Last line. |
| `%` | Entire file (shorthand for `1,$`). |

## Visual Mode Operations (Vim only)

Select text and then apply Normal mode commands.

1.  Enter Visual mode (<kbd>v</kbd>, <kbd>V</kbd>, or <kbd>Ctrl</kbd>+<kbd>v</kbd>).
2.  Move the cursor to select the desired text.
3.  Execute a Normal mode command (e.g., `d` to delete, `y` to yank, `>` to indent, `<` to outdent).

## Window Management (Vim only)

Work with multiple files or views of the same file simultaneously.

| Command | Description |
| :------ | :----------- |
| `:sp` | Split current window horizontally. |
| `:vsp` | Split current window vertically. |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>w</kbd> | Cycle through windows. |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>h</kbd> | Move to the window on the left. |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>l</kbd> | Move to the window on the right. |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>j</kbd> | Move to the window below. |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>k</kbd> | Move to the window above. |
| `:q` | Close the current window. |
| `:only` | Make the current window the only one. |

## Configuration (.vimrc)

Customize `Vim` to your preferences by creating or editing the `.vimrc` file in your home directory (`~/.vimrc`).

Example additions to `.vimrc`:

```vim
set nu            " Show line numbers
set autoindent    " Auto-indent new lines
set tabstop=4     " Number of spaces a <Tab> in the file counts for
set shiftwidth=4  " Number of spaces to use for each step of (auto)indent
set expandtab     " Use spaces instead of tabs
syntax on         " Enable syntax highlighting
filetype plugin indent on " Enable file type detection, plugins, and indenting
```

## Further Learning & Practice

*   **`vimtutor`**: The best place to start! Type `vimtutor` in your terminal for an interactive, self-paced tutorial that teaches the basics.
*   **Online Resources**: Many websites offer interactive `vim` games and tutorials. Search for "vim game" or "learn vim interactively".
*   **Practice, Practice, Practice**: The key to mastering `vi`/`Vim` is consistent practice. Try to use it for all your text editing tasks, even simple ones.

---

## Contribute

Any contributions, suggestions, or corrections are highly welcome! Feel free to open an issue or pull request.
