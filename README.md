# ZSH Setup

Languages: [🇪🇸] [Español](README.ES.md) - [🇺🇸] [English](README.md)

ZSH setup and productivity tools for developers

## Repo

### 1. Clone

On `~` (home) path clone this repo

```bash
git init 
git remote add origin https://github.com/deinacademy/zsh-setup.git
git pull origin main
```

### 2. Setup

On `.zshrc` file add.

```bash
# Helpers
export WINHOME=$(wslpath "$(wslvar USERPROFILE)")
export OPEN="explorer.exe" #wsl2
export BROWSER="${OPEN}" #wsl2

export PATH="$HOME/.helpers/b64/:$PATH"
export PATH="$HOME/.helpers/git/:$PATH"
export PATH="$HOME/.helpers/md/:$PATH"
export PATH="$HOME/.helpers/open/:$PATH"
chmod +x ~/.helpers/**/*

# Custom

export GIT_USER_NAME="user" # private business/work user
export GIT_USER_EMAIL="user@mail.com" # private business/work e-mail
export GITHUB_USER_NAME="user" # public personal user
export GITHUB_USER_EMAIL="user@users.noreply.github.com" # public personal e-mail
[ -f ~/.aliases ] && . ~/.aliases
[ -f ~/.colors ] && . ~/.colors
[ -f ~/.hooks ] && . ~/.hooks
```

> `OPEN` and `BROWSE` constants need to be configured according yor OS. Windows (WSL2) and macOS use the same command to open the file explorer or the default web browser, on Ubuntu (Linux) need to be specified each one.

|SO|`OPEN`|`BROWSER`|
|---|---|---|
|Windows (WSL2)|`"explorer.exe"`|`"${OPEN}"`|
|macOS|`"open"`|`"${OPEN}"`|
|Ubuntu|`"xdg-open"`, `"gnome-open"`, `"nautilus"` ...|`"googlechrome"`, `"firefox"` ...|

### 3. Permissions

Now add execution permission:

```bash
chmod +x ~/.helpers/**/*
```

### 4. Update

Once finish, save `.zshrc` file, close and reopen all terminals or update his source running `source ~/.zshrc` command.

That's all folks! It's ready to use.

## Folder Structure

```bash
~
├── .cheatsheet
│   └── git.md
│   └── open.md
├── .helpers
│   ├── b64
│   ├── git
│   ├── md
│   ├── open
│   └── react
├── .aliases
├── .colors
├── .hooks
└── .zshrc
```

|Name|Description|
|---|---|
|`.cheatsheet`| Folder with basic markdown file to see a cheatsheet with `helpers` and `alias` |
|`.helpers`| Folder with custom helper functions to use as terminal commands |
| ── `b64`| Helper commands for file conversions to/from base64 |
| ── `git`| Helper commands for git cloning with extra features (WIP) |
| ── `md`| Helper commands to see MarkDown files on terminal (WIP) |
| ── `open`| Helper commands to open file/folder on the File Explorer or open files/url on the Browser |
| ── `react`| Helper commands to create React project with extra features (WIP) |
|`.aliases`| File for aliases definitions |
|`.colors`| File with terminal colors to use in other scripts |
|`.hooks`| ZSH hooks file with custom functions to run as validation before and after run commands |
|`.zshrc`| ZSH source file |

## Article Series

- [Useful Alias for ZSH](https://dev.to/equiman/useful-alias-for-zsh-1j8b)
- [Reveal the command behind an alias with ZSH](https://dev.to/equiman/reveal-the-command-behind-an-alias-with-zsh-4d96)
- [Command validations with ZSH](https://dev.to/equiman/command-validations-with-zsh-2boa)
- [Open File Explorer and Browser from ZSH](https://dev.to/equiman/open-file-explorer-and-browser-mbb)
- [Automatic change directory after git clone](https://dev.to/equiman/automatic-change-directory-after-git-clone-8ei)
- [ZSH cheatsheet for git plugin](https://dev.to/equiman/zsh-cheatsheet-for-git-plugin-1f6a)
- [base64 encode/decode multiple files](https://dev.to/equiman/base64-encode-decode-multiple-files-2ol1)
