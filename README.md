# ✨ Master the `vi` & `Vim` Editors (Enhanced Guide) ✨

Welcome to this comprehensive and enhanced guide for mastering the powerful `vi` and `Vim` text editors! While `vi` is a foundational classic, `Vim` (Vi IMproved) extends it with a wealth of features that make it an indispensable tool for efficient text manipulation. This guide will cover the core fundamentals of `vi` and progressively introduce you to many of `Vim`'s advanced capabilities, empowering you to navigate, edit, and create with speed and precision.

---

## 🚀 Getting Started

To launch the editor and open or create a file:

```bash
vim filename   # ✨ Recommended: Use `vim` for enhanced features and modern experience
vi filename    # Classic `vi` editor
```

---

## 🚦 Operating Modes: The Heart of `vi`/`Vim`

`vi`/`Vim` operates on the principle of **modal editing**, utilizing distinct modes for different tasks. This modal design is a cornerstone of its efficiency and power once mastered.

### 1. Normal Mode (Command Mode)

This is the **default mode** when you open `vi`/`Vim`. In Normal Mode, every keypress is interpreted as a **command** to navigate, delete, copy, paste, or manipulate text objects. **You do not type text directly here.**

| Key | Description |
| :------------------ | :--------------------------------------------------------------------------------------------------------- |
| <kbd>ESC</kbd> | The most crucial key: **Returns you to Normal Mode** from any other mode. Essential for resetting your state. |
| <kbd>Ctrl</kbd>+<kbd>[</kbd> | An effective alternative to <kbd>ESC</kbd>, often more comfortable for touch typists. |

### 2. Insert Mode

This is where you **type or insert text** into the buffer. All characters you type are directly entered into the file, just like a conventional text editor.

| Key | Description | Reverse/Alternative | Description |
| :------ | :--------------------------------- | :-------------------- | :--------------------------------------------- |
| <kbd>i</kbd> | Insert text **before** the cursor. | <kbd>I</kbd> | Insert text at the **start** of the current line. |
| <kbd>a</kbd> | Insert text **after** the cursor. | <kbd>A</kbd> | Insert text at the **end** of the current line. |
| <kbd>o</kbd> | Open a **new line below** the current line and enter Insert Mode. | <kbd>O</kbd> | Open a **new line above** the current line and enter Insert Mode. |
| <kbd>s</kbd> | Delete character under cursor and enter Insert Mode. | <kbd>S</kbd> | Delete the entire current line and enter Insert Mode. |

### 3. Visual Mode (Vim Exclusive)

Visual Mode allows you to **select blocks of text** interactively using your cursor keys, similar to how you might select text with a mouse in other editors. Once text is selected, you can apply various Normal Mode commands (e.g., delete, yank, change) to the entire selection.

| Key | Description |
| :---------------------- | :------------------------------------------------------------------------------------------ |
| <kbd>v</kbd> | Enters **character-wise** Visual Mode (selects individual characters). |
| <kbd>V</kbd> | Enters **line-wise** Visual Mode (selects entire lines). |
| <kbd>Ctrl</kbd>+<kbd>v</kbd> | Enters **block-wise** Visual Mode (selects rectangular blocks of text). |

### 4. Command-Line Mode (Ex Mode)

Accessed by typing `:` from Normal Mode. This powerful mode allows you to execute commands that often affect multiple lines or the entire file, such as saving, quitting, complex search/replace operations, and file management.

---

## 🗺️ Basic Navigation (Normal Mode)

Efficient movement is fundamental to mastering `vi`/`Vim`. Combine these commands with counts (e.g., `5j` to move down 5 lines).

| Key | Description | Key | Description |
| :-------------------------- | :---------------------------------------------- | :-------------------------- | :---------------------------------------------- |
| <kbd>h</kbd> | Move cursor **left**. | <kbd>l</kbd> | Move cursor **right**. |
| <kbd>j</kbd> | Move cursor **down**. | <kbd>k</kbd> | Move cursor **up**. |
| <kbd>w</kbd> | Move to the start of the **next word**. | <kbd>b</kbd> | Move to the start of the **previous word**. |
| <kbd>e</kbd> | Move to the **end** of the current word. | <kbd>0</kbd> (zero) | Move to the **start** of the line. |
| <kbd>$</kbd> | Move to the **end** of the line. | <kbd>^</kbd> | Move to the first **non-blank character** of the line. |
| <kbd>gg</kbd> | Go to the **first line** of the file. | <kbd>G</kbd> | Go to the **last line** of the file. |
| <kbd>5gg</kbd> or <kbd>5G</kbd> | Go to **line 5**. | <kbd>H</kbd> | Move to the **top** of the visible screen. |
| <kbd>M</kbd> | Move to the **middle** of the visible screen. | <kbd>L</kbd> | Move to the **bottom** of the visible screen. |
| <kbd>Ctrl</kbd>+<kbd>f</kbd> | Scroll **forward** one full screen. | <kbd>Ctrl</kbd>+<kbd>b</kbd> | Scroll **backward** one full screen. |
| <kbd>Ctrl</kbd>+<kbd>d</kbd> | Scroll **down** half a screen. | <kbd>Ctrl</kbd>+<kbd>u</kbd> | Scroll **up** half a screen. |

---

## 💾 Saving & Quitting (Command-Line Mode)

**Always return to Normal Mode** (<kbd>ESC</kbd>) before entering Command-Line Mode with `:`.

| Command | Description |
| :------------ | :---------------------------------------------------------------------------- |
| `:w` | Save the file without quitting. |
| `:q` | Quit the editor (only if no unsaved changes exist). |
| `:wq` or <kbd>ZZ</kbd> | Save changes and then quit the editor. |
| `:x` or <kbd>ZQ</kbd> | Similar to `:wq`, but only writes to file if changes were made. |
| `:q!` | **Force quit** the editor without saving any changes. Use with caution! |
| `:w filename` | Save the contents of the current buffer to a new file named `filename`. |
| `:saveas filename` | Saves the current buffer to `filename` and makes `filename` the current buffer. |
| `:qa!` | Quit **all** open buffers/windows without saving any changes (force all). |

---

## ↩️ Undo, Redo & Repeat (Normal Mode)

These commands are essential for correcting mistakes and efficiently repeating actions.

| Command | Description |
| :-------------------------- | :--------------------------------------------------- |
| <kbd>u</kbd> | **Undo** the last change. |
| <kbd>Ctrl</kbd>+<kbd>r</kbd> | **Redo** the last undone change. |
| <kbd>.</kbd> | **Repeat** the last change (an incredibly powerful command!). |

---

## ✂️ Deleting, Copying & Pasting (Normal Mode)

These commands are often combined with **motions** (e.g., `w` for word, `$` for end of line) to specify *what* text to act upon.

| Command | Description | Example Usage |
| :------ | :----------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `d` | **Delete** (cut) text. | `dw` (delete word), `d$` (delete to end of line), `dd` (delete current line), `dG` (delete to end of file). |
| `y` | **Yank** (copy) text. | `yw` (yank word), `y$` (yank to end of line), `yy` (yank current line), `yG` (yank to end of file). |
| `p` | **Paste** the most recently yanked/deleted text **after** the cursor (or below the current line for whole lines). | |
| `P` | **Paste** the most recently yanked/deleted text **before** the cursor (or above the current line for whole lines). | |
| `x` | Delete the character **under** the cursor. | |
| `X` | Delete the character **before** the cursor. | |

**⚡ Using Counts**: Prefix most commands with a number to repeat the action.
*   `5dd`: Delete 5 lines.
*   `3yw`: Yank 3 words.

---

## 🔎 Search and Replace (Command-Line Mode)

`vi`/`Vim` offers robust search and replace functionalities, supporting regular expressions for powerful pattern matching.

| Command | Description |
| :--------------- | :---------------------------------------------------------------------- |
| `/pattern` | Search **forward** for `pattern`. |
| `?pattern` | Search **backward** for `pattern`. |
| <kbd>n</kbd> | Repeat the last search in the **same direction**. |
| <kbd>N</kbd> | Repeat the last search in the **opposite direction**. |
| `:s/old/new/` | Replace the **first** occurrence of `old` with `new` on the **current line**. |
| `:s/old/new/g` | Replace **all** occurrences of `old` with `new` on the **current line** (`g` for global). |
| `:%s/old/new/g` | Replace **all** occurrences of `old` with `new` throughout the **entire file**. |
| `:%s/old/new/gc` | Replace all occurrences, but **confirm** each replacement with `c` (confirm). |
| `:n,ms/old/new/g` | Replace `old` with `new` globally between line `n` and line `m`. |

**Address Explanations (for `:s` commands):**

| Address | Description |
| :------ | :-------------------------------------------------- |
| `.` | Refers to the **current line**. |
| `n` | Specifies line number `n`. |
| `.+m` | Refers to the current line plus `m` lines (e.g., `.+3` is 3 lines below). |
| `$` | Refers to the **last line** of the file. |
| `%` | A convenient shorthand for the **entire file** (`1,$`). |

---

## 🎯 Visual Mode Operations (Vim Exclusive)

Once in Visual Mode (using <kbd>v</kbd>, <kbd>V</kbd>, or <kbd>Ctrl</kbd>+<kbd>v</kbd>), you select text by moving the cursor. After selection, apply a Normal Mode command to the highlighted block.

1.  Enter Visual Mode: Choose <kbd>v</kbd> (character), <kbd>V</kbd> (line), or <kbd>Ctrl</kbd>+<kbd>v</kbd> (block).
2.  **Select Text**: Move your cursor using navigation commands to highlight the desired text.
3.  **Apply Command**: Press a Normal Mode command (e.g., `d` to delete, `y` to yank, `>` to indent, `<` to outdent).

---

## 🖥️ Window Management (Vim Exclusive)

`Vim` allows you to work with multiple files or different views of the same file simultaneously within its interface, significantly boosting productivity.

| Command | Description |
| :-------------------------- | :------------------------------------------------------------------------------------- |
| `:sp` | **Split** the current window **horizontally** (creates a new buffer for editing). |
| `:vsp` | **Split** the current window **vertically** (creates a new buffer for editing). |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>w</kbd> | Cycle through **open windows**. |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>h</kbd> | Move to the window on the **left**. |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>l</kbd> | Move to the window on the **right**. |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>j</kbd> | Move to the window **below**. |
| <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>k</kbd> | Move to the window **above**. |
| `:q` | Close the **current window**. |
| `:only` | Close all other windows, making the current window the **only one** visible. |

---

## ⚙️ Configuration (`.vimrc`)

Personalize your `Vim` experience by creating or editing the `.vimrc` file located in your home directory (`~/.vimrc`). This file executes commands every time `Vim` starts.

**Example additions to `~/.vimrc`:**

```vim
" Display line numbers
set nu

" Automatically indent new lines
set autoindent

" Set tab character to display as 4 spaces wide
set tabstop=4

" Set the number of spaces for (auto)indentation
set shiftwidth=4

" Use spaces instead of actual tab characters
set expandtab

" Enable syntax highlighting for various file types
syntax on

" Enable file type detection, plugin loading for file types, and smart indentation
filetype plugin indent on
```

---

## 📚 Further Learning & Practice

The true path to `vi`/`Vim` mastery is consistent practice and exploration.

*   **`vimtutor`**: The **absolute best starting point**! Simply type `vimtutor` in your terminal for an interactive, self-paced, and highly effective tutorial built right into `Vim`.
*   **Online Resources**: Explore various interactive `Vim` games and tutorials available online. Search for terms like "vim game" or "learn vim interactively" to find engaging practice tools.
*   **Practice, Practice, Practice**: The most crucial advice. Make a conscious effort to use `vi`/`Vim` for all your text editing needs, no matter how small. Muscle memory is key!

---

## 🤝 Contribute

Your contributions, suggestions, and corrections are highly valued! Please feel free to open an issue or submit a pull request if you have ideas for improving this guide.
