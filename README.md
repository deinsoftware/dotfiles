# ZSH Setup

Languages: [[ES]](README.ES.md) - [[EN]](README.md)

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
export OPEN="explorer.exe" #wsl2
export BROWSER=""${OPEN}"" #wsl2

export PATH="$HOME/.helpers/b64/:$PATH"
export PATH="$HOME/.helpers/git/:$PATH"
export PATH="$HOME/.helpers/md/:$PATH"
export PATH="$HOME/.helpers/open/:$PATH"
chmod +x ~/.helpers/**/*

# Custom
local WINHOME=$(wslpath "$(wslvar USERPROFILE)")

local GIT_USER_NAME="user" # private business/work user
local GIT_USER_EMAIL="user@mail.com" # private business/work e-mail
local GITHUB_USER_NAME="user" # public personal user
local GITHUB_USER_EMAIL="user@users.noreply.github.com" # public personal e-mail
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
|`.aliases`| File for aliases definitions |
|`.colors`| File with terminal colors to use in other scripts |
|`.hooks`| ZSH hooks file with custom functions to run as validation before and after run commands |
|`.zshrc`| ZSH source file |

## Article Series

- [Reveal the command behind an alias with ZSH](https://dev.to/equiman/reveal-the-command-behind-an-alias-with-zsh-4d96)
- [Useful Alias for ZSH](https://dev.to/equiman/useful-alias-for-zsh-1j8b)
- [Automatic change directory after git clone](https://dev.to/equiman/automatic-change-directory-after-git-clone-8ei)
- [Command validations with ZSH](https://dev.to/equiman/command-validations-with-zsh-2boa)
- [Open File Explorer and Browser from ZSH](https://dev.to/equiman/open-file-explorer-and-browser-mbb)
- [ZSH cheatsheet for git plugin](https://dev.to/equiman/zsh-cheatsheet-for-git-plugin-1f6a)
- [base64 encode/decode multiple files](https://dev.to/equiman/base64-encode-decode-multiple-files-2ol1)
