# 02: Terminal basics

## Why this matters

The terminal (also called the command line or shell) is how developers run programs, use Git, install tools and talk to servers. Graphical tools come and go, but the terminal is everywhere, including on every server you'll ever deploy to.

## Key ideas

### Which terminal?

| OS | Use |
|---|---|
| Windows | **Git Bash** (installed with Git for Windows), or **PowerShell**. WSL (Linux on Windows) is great later. |
| macOS | **Terminal** or iTerm2. The default shell is `zsh`. |
| Linux | Your distro's terminal. The shell is usually `bash`. |

This curriculum shows commands in **bash/zsh** syntax, which also works in Git Bash on Windows.

### The prompt and the working directory

When you open a terminal, you're "standing" in a folder called the **working directory**. Every command runs from there.

```bash
pwd                 # print working directory: where am I?
ls                  # list files here (PowerShell: ls or dir)
ls -la              # list everything, including hidden files, with details
cd projects         # change directory into "projects"
cd ..               # go up one level
cd ~                # go to your home folder
```

### Paths

- **Absolute path**: starts from the root. `/home/ana/code/app` or `C:\Users\Ana\code\app`.
- **Relative path**: starts from where you are. `code/app`, `../notes`.
- `.` means "this folder" and `..` means "the parent folder".
- Paths with spaces need quotes: `cd "My Projects"`.

### Files and folders

```bash
mkdir notes               # make a folder
mkdir -p a/b/c            # make nested folders
touch todo.txt            # create an empty file (PowerShell: New-Item todo.txt)
cat todo.txt              # print a file's contents
cp todo.txt backup.txt    # copy
mv backup.txt old.txt     # move / rename
rm old.txt                # delete. There is NO recycle bin. Be careful.
```

### Running programs

```bash
python --version          # most tools support --version
python hello.py           # run a program with an argument
node app.js
```

If a command "is not recognized" or "not found", it's either not installed or not on your **PATH**, the list of folders the shell searches for programs.

### Productivity tricks

- **Tab** autocompletes file and folder names. Use it constantly.
- **↑ / ↓** scroll through previous commands.
- **Ctrl + C** stops a running program.
- **Ctrl + L** or `clear` clears the screen.
- `command --help` or `man command` shows help.

## Exercise

Using only the terminal:

1. Create a folder `terminal-practice` in your home directory, and `cd` into it.
2. Create the folders `drafts` and `final`, and a file `drafts/idea.txt`.
3. Write a line into it: `echo "my first idea" > drafts/idea.txt`. Print it with `cat`.
4. Copy it to `final/idea.txt`, then list both folders.
5. Delete the whole `terminal-practice` folder (`cd ..` first, then `rm -r terminal-practice`).

## Check your understanding

1. What's the difference between `cd notes` and `cd /notes`?
2. You type `python` and get "command not found". Give two possible reasons.
3. Why should you be extra careful with `rm`?

## Further reading

- [The Missing Semester: The Shell (MIT)](https://missing.csail.mit.edu/2020/course-shell/)
- [Command line crash course (MDN)](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line)
