# dotfiles

Languages: [🇪🇸] [Español](README.ES.md) - [🇺🇸] [English](README.md)

ZSH setup and productivity tools for development

## Repo

### 1. Clone

On  `~/.dotfiles` path clone this repo

```bash
git clone https://github.com/deinsoftware/dotfiles.git ~/.dotfiles
```

### 2. Setup

On `.zshrc` file add.

```bash
# Default branches
export MAIN="main"
export DEV="dev"

# Helpers
export WINHOME=$(wslpath "$(wslvar USERPROFILE)")
export OPEN="wslview" #wsl2
export BROWSER="${OPEN}" #wsl2

export PATH="$HOME/.dotfiles/helpers/b64/:$PATH"
export PATH="$HOME/.dotfiles/helpers/code/:$PATH"
export PATH="$HOME/.dotfiles/helpers/md/:$PATH"
export PATH="$HOME/.dotfiles/helpers/open/:$PATH"
export PATH="$HOME/.dotfiles/helpers/search/:$PATH"
export PATH="$HOME/.dotfiles/helpers/terminal/:$PATH"
chmod +x ~/.dotfiles/helpers/**/* ~/.dotfiles/helpers/**/.[!.]*

# Custom
[ -f ~/.dotfiles/.aliases ] && . ~/.dotfiles/.aliases
[ -f ~/.dotfiles/.colors ] && . ~/.dotfiles/.colors
[ -f ~/.dotfiles/.hooks ] && . ~/.dotfiles/.hooks
```

> `OPEN` and `BROWSE` constants need to be configured according yor OS. Windows (WSL2) and macOS use the same command to open the file explorer or the default web browser, on Ubuntu (Linux) need to be specified each one.

| SO                | `OPEN`                                         | `BROWSER`                         |
| ----------------- | ---------------------------------------------- | --------------------------------- |
| Windows (GitBash) | `"explorer.exe"`                               | `"${OPEN}"`                       |
| Windows (WSL2)    | `"wslview"`                                    | `"${OPEN}"`                       |
| macOS             | `"open"`                                       | `"${OPEN}"`                       |
| Ubuntu            | `"xdg-open"`, `"gnome-open"`, `"nautilus"` ... | `"googlechrome"`, `"firefox"` ... |

> On WSL require to install [wslu](https://wslutiliti.es)

### 3. Permissions

Now add execution permission:

```bash
chmod +x ~/.dotfiles/helpers/**/* ~/.dotfiles/helpers/**/.[!.]*
```

### 4. Update

Once finish, save `.zshrc` file, close and reopen all terminals or update his source running `source ~/.zshrc` command.

That's all folks! It's ready to use.

## Folder Structure

```bash
~
└── .zshrc
└── .dotfiles
    ├── cheatsheet
    │   └── git.md
    │   └── open.md
    ├── helpers
    │   ├── b64
    │   ├── code
    │   ├── md
    │   ├── open
    │   ├── search
    │   └── terminal
    ├── .aliases
    ├── .colors
    └── .hooks
```

|Name|Description|
|---|---|
|`.zshrc`| ZSH source file |
|`cheatsheet`| Folder with basic markdown file to see a cheatsheet with `helpers` and `alias` |
|`helpers`| Folder with custom helper functions to use as terminal commands |
| ── `b64`| Helper commands for file conversions to/from base64 |
| ── `code`| Helper commands to open VSCode |
| ── `md`| Helper commands to see MarkDown files on terminal (WIP) |
| ── `open`| Helper commands to open file/folder on the File Explorer or open files/url on the Browser |
| ── `search`| Helper commands to search text inside files |
| ── `terminal`| Helper commands to talk with the OS |
|`.aliases`| File for aliases definitions |
|`.colors`| File with terminal colors to use in other scripts |
|`.hooks`| ZSH hooks file with custom functions to run as validation before and after run commands |

## ZSH plugins

There are a lot of [plugins for ZSH](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins), those are the most useful that I found.

### Official

* [adb](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/adb)
* [command-not-found](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/command-not-found)
* [deno](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/deno)
* [docker](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/docker)
* [git](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/git)
* [git-lfs](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/git-lfs)
* [github](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/github)
* [gitignore](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/gitignore)
* [history-substring-search](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/history-substring-search)
* [node](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/node)
* [npm](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/npm)
* [yarn](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/yarn)
* [volta](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/volta)
* [vscode](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/vscode)
* [sudo](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/sudo)
* [ubuntu](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/ubuntu)
* [web-search](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/web-search)
* [z](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/z)

### Extras

* [zsh-nvm](https://github.com/lukechilds/zsh-nvm)
* [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
* [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)

## Article Series

* [Useful Alias for ZSH](https://dev.to/equiman/useful-alias-for-zsh-1j8b)
* [Reveal the command behind an alias with ZSH](https://dev.to/equiman/reveal-the-command-behind-an-alias-with-zsh-4d96)
* [Command validations with ZSH](https://dev.to/equiman/command-validations-with-zsh-2boa)
* [Open File Explorer and Browser from ZSH](https://dev.to/equiman/open-file-explorer-and-browser-mbb)
* [ZSH cheatsheet for git plugin](https://dev.to/equiman/zsh-cheatsheet-for-git-plugin-1f6a)
* [Move WSL File System to another Drive](https://dev.to/equiman/move-wsl-file-system-to-another-drive-2a3d)
* [ZSH on Windows without WSL](https://dev.to/equiman/zsh-on-windows-without-wsl-4ah9)

---

## About

### Built With

* [VS Code](https://code.visualstudio.com/) - Code editing redefined.
* [Widows Terminal](https://github.com/Microsoft/Terminal/) - A modern terminal application for users of command-line tools and shells.

### Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [ZSH Dev Toolkit](https://github.com/deinsoftware/zsh-dev-toolkit/tags) on GitHub.

### Authors

* **Camilo Martinez** [Equiman](http://github.com/equiman)]

See also the list of [contributors](https://github.com/deinsoftware/zsh-dev-toolkit/contributors) who participated in this project.

### Sponsors

If this project helps you, consider buying me a cup of coffee.

[![GitHub Sponsors](https://img.shields.io/badge/-GitHub%20Sponsors-gray?style=flat&labelColor=171515&logo=github&logoColor=white&link=https://github.com/sponsors/deinsoftware)](https://github.com/sponsors/deinsoftware)
[![paypal](https://img.shields.io/badge/-PayPal-gray?style=flat&labelColor=00457C&logo=paypal&logoColor=white&link=https://paypal.me/equiman/3)](https://paypal.me/equiman/3)

### License

This project is licensed under the MIT License - see the [LICENSE](LICENSE.md) file for details.
