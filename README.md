# Learn `vi` and `Vim` Editors

Welcome to this guide for learning the powerful `vi` and `Vim` text editors. `Vim` (Vi IMproved) builds on the classic `vi` with many extra features. This guide will teach you the basics of `vi` and then show you some of `Vim`'s powerful tools. Our goal is to help you edit text quickly and effectively.

---

## Getting Started

To open or create a file with `vi` or `vim`:

```bash
vim filename   # Use `vim` for more features
vi filename    # Use classic `vi`
```

---

## How `vi`/`Vim` Works: Operating Modes

`vi` and `Vim` use different "modes" for different tasks. This way of working makes them very efficient once you learn it.

### 1. Normal Mode (Command Mode)

This is the main mode when you open `vi`/`Vim`. In Normal Mode, pressing keys runs **commands** to move around, delete, copy, paste, or change text. **You do not type text directly in this mode.**

| Key | What it Does |
| :------------------ | :----------------------------------------------------------------------------------------- |
| <kbd>ESC</kbd> | The most important key: Always brings you back to **Normal Mode** from any other mode. |
| <kbd>Ctrl</kbd>+<kbd>[</kbd> | Another way to get back to <kbd>Normal Mode</kbd>, often easier to type. |

### 2. Insert Mode

In Insert Mode, you **type text** into your file. Everything you type goes directly into the file, like in other text editors.

| Key | What it Does | Another Key | What it Does |
| :------ | :------------------------ | :-------------------- | :---------------------------------- |
| <kbd>i</kbd> | Start typing **before** the cursor. | <kbd>I</kbd> | Start typing at the **start** of the line. |
| <kbd>a</kbd> | Start typing **after** the cursor. | <kbd>A</kbd> | Start typing at the **end** of the line. |
| <kbd>o</kbd> | Make a **new line below** and start typing. | <kbd>O</kbd> | Make a **new line above** and start typing. |
| <kbd>s</kbd> | Delete the character under the cursor and start typing. | <kbd>S</kbd> | Delete the whole line and start typing. |

### 3. Visual Mode (Vim Only)

Visual Mode lets you **select parts of your text** with your cursor, like using a mouse to highlight. Once text is selected, you can use Normal Mode commands (like delete, copy, change) on the selected part.

| Key | What it Does |
| :---------------------- | :----------------------------------------------------------------------------- |
| <kbd>v</kbd> | Select text **character by character**. |
| <kbd>V</kbd> | Select text **line by line**. |
| <kbd>Ctrl</kbd>+<kbd>v</kbd> | Select text in a **rectangle shape**. |

### 4. Command-Line Mode (Ex Mode)

You enter this mode by typing `:` from Normal Mode. Here, you can run powerful commands that affect many lines or the whole file, such as saving, quitting, finding/replacing text, and managing files.

---

## Moving Around (Normal Mode)

Learning to move your cursor quickly is a key skill in `vi`/`Vim`. You can add a number before these commands to repeat them (e.g., `5j` moves down 5 lines).

| Key | What it Does | Key | What it Does |
| :-------------------------- | :---------------------------------- | :-------------------------- | :---------------------------------- |
| <kbd>h</kbd> | Move cursor **left**. | <kbd>l</kbd> | Move cursor **right**. |
| <kbd>j</kbd> | Move cursor **down**. | <kbd>k</kbd> | Move cursor **up**. |
| <kbd>w</kbd> | Go to the start of the **next word**. | <kbd>b</kbd> | Go to the start of the **previous word**. |
| <kbd>e</kbd> | Go to the **end** of the current word. | <kbd>0</kbd> (zero) | Go to the **start** of the line. |
| <kbd>$</kbd> | Go to the **end** of the line. | <kbd>^</kbd> | Go to the first **text character** of the line. |
| <kbd>gg</kbd> | Go to the **very first line** of the file. | <kbd>G</kbd> | Go to the **very last line** of the file. |
| <kbd>5gg</kbd> or <kbd>5G</kbd> | Go to **line 5**. | <kbd>H</kbd> | Go to the **top** of the screen. |
| <kbd>M</kbd> | Go to the **middle** of the screen. | <kbd>L</kbd> | Go to the **bottom** of the screen. |
| <kbd>Ctrl</kbd>+<kbd>f</kbd> | Scroll **forward** one full screen. | <kbd>Ctrl</kbd>+<kbd>b</kbd> | Scroll **backward** one full screen. |
| <kbd>Ctrl</kbd>+<kbd>d</kbd> | Scroll **down** half a screen. | <kbd>Ctrl</kbd>+<kbd>u</kbd> | Scroll **up** half a screen. |

---

## Saving & Quitting (Command-Line Mode)

Always go back to Normal Mode (<kbd>ESC</kbd>) before typing `:` commands.

| Command | What it Does |
| :------------ | :-------------------------------------------------------------------- |
| `:w` | Save the file without closing it. |
| `:q` | Close the editor (only if you haven't made any changes). |
| `:wq` or <kbd>ZZ</kbd> | Save changes and then close the editor. |
| `:x` or <kbd>ZQ</kbd> | Like `:wq`, but only saves if you made changes. |
| `:q!` | **Close the editor without saving changes.** Be careful when using this! |
| `:w filename` | Save the current file to a **new file** named `filename`. |
| `:saveas filename` | Save the current file to `filename` and start editing `filename` instead. |
| `:qa!` | Close **all open files** without saving any changes. |

---

## Undo, Redo & Repeat (Normal Mode)

These commands help you fix mistakes and do actions again.

| Command | What it Does |
| :-------------------------- | :-------------------------------------------------- |
| <kbd>u</kbd> | **Undo** your last change. |
| <kbd>Ctrl</kbd>+<kbd>r</kbd> | **Redo** a change you just undid. |
| <kbd>.</kbd> | **Repeat** your very last action (extremely useful!). |

---

## Deleting, Copying & Pasting (Normal Mode)

These commands work with **motions** (like `w` for word, `$` for end of line) to tell `vi`/`Vim` what text to act on.

| Command | What it Does | Example |
| :------ | :----------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------- |
| `d` | **Delete** (cut) text. | `dw` (delete word), `d$` (delete to end of line), `dd` (delete current line), `dG` (delete to end of file). |
| `y` | **Yank** (copy) text. | `yw` (yank word), `y$` (yank to end of line), `yy` (yank current line), `yG` (yank to end of file). |
| `p` | **Paste** the copied/cut text **after** the cursor (or below the line). | |
| `P` | **Paste** the copied/cut text **before** the cursor (or above the line). | |
| `x` | Delete the character **under** the cursor. | |
| `X` | Delete the character **before** the cursor. | |

**Using Counts**: Put a number before most commands to do them that many times.
*   `5dd`: Delete 5 lines.
*   `3yw`: Copy 3 words.

---

## Finding and Replacing Text (Command-Line Mode)

`vi` and `Vim` have strong tools to find and change text, even using special patterns (regular expressions).

| Command | What it Does |
| :--------------- | :---------------------------------------------------- |
| `/pattern` | Search **forward** for `pattern`. |
| `?pattern` | Search **backward** for `pattern`. |
| <kbd>n</kbd> | Repeat the last search in the **same direction**. |
| <kbd>N</kbd> | Repeat the last search in the **opposite direction**. |
| `:s/old/new/` | Change the **first** `old` to `new` on the **current line**. |
| `:s/old/new/g` | Change **all** `old` to `new` on the **current line** (`g` means all). |
| `:%s/old/new/g` | Change **all** `old` to `new` in the **whole file**. |
| `:%s/old/new/gc` | Change all `old` to `new`, but **ask you to confirm** each change. |
| `:n,ms/old/new/g` | Change `old` to `new` between line `n` and line `m`. |

**Where to Search (Addresses for `:s` commands):**

| Address | What it Means |
| :------ | :------------------------------------------------------ |
| `.` | The **current line**. |
| `n` | Line number `n`. |
| `.+m` | The current line plus `m` lines (e.g., `.+3` is 3 lines down). |
| `$` | The **last line** of the file. |
| `%` | A quick way to say the **whole file** (from line 1 to the end). |

---

## Visual Mode Actions (Vim Only)

After you enter Visual Mode (using <kbd>v</kbd>, <kbd>V</kbd>, or <kbd>Ctrl</kbd>+<kbd>v</kbd>), you select text by moving your cursor. Then, you can use a Normal Mode command on the selected text.

1.  Enter Visual Mode: Use <kbd>v</kbd> (for characters), <kbd>V</kbd> (for lines), or <kbd>Ctrl</kbd>+<kbd>v</kbd> (for blocks).
2.  **Select Text**: Move your cursor to highlight the text you want.
3.  **Do Command**: Press a Normal Mode command (like `d` to delete, `y` to copy, `>` to indent, `<` to unindent).

---

## Working with Windows (Vim Only)

`Vim` lets you open multiple files or different parts of the same file at once, which can help you work faster.

| Command | What it Does |
| :-------------------------- | :-------------------------------------------------------------------------------- |
| `:sp` | **Split** the window **horizontally** (creates a new space for editing). |
| `:vsp` | **Split** the window **vertically** (creates a new space for editing). |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>w</kbd> | Move to the **next window**. |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>h</kbd> | Move to the window on the **left**. |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>l</kbd> | Move to the window on the **right**. |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>j</kbd> | Move to the window **below**. |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>k</kbd> | Move to the window **above**. |
| `:q` | Close the **current window**. |
| `:only` | Close all other windows, so only the current one is open. |

---

## Setting Up `Vim` (`.vimrc`)

You can change how `Vim` works by making or editing the `.vimrc` file in your home folder (`~/.vimrc`). This file runs commands every time `Vim` starts.

**Example settings for `~/.vimrc`:**

```vim
" Show line numbers
set nu

" Automatically make new lines indent correctly
set autoindent

" Tabs will look like 4 spaces wide
set tabstop=4

" When you indent, it will move by 4 spaces
set shiftwidth=4

" Use spaces instead of actual tab characters
set expandtab

" Turn on color highlighting for code
syntax on

" Turn on features for different file types (plugins, indenting)
filetype plugin indent on
```

---

## More Learning & Practice

The best way to become good at `vi`/`Vim` is to practice a lot and keep exploring.

*   **`vimtutor`**: This is the **best place to begin**! Just type `vimtutor` in your terminal. It's an interactive lesson built into `Vim` that teaches you the basics step-by-step.
*   **Online Tools**: Look for `Vim` games and lessons online. Search for "vim game" or "learn vim interactively".
*   **Practice Every Day**: The most important tip! Try to use `vi`/`Vim` for all your text editing, even small tasks. This helps you remember the commands without thinking.

---

## Contribute

Your help, ideas, and corrections are very welcome! If you have ways to make this guide better, please open an issue or send a pull request.
