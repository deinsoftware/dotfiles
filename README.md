# dotfiles

Languages: [🇪🇸] [Español](README.ES.md) - [🇺🇸] [English](README.md)

ZSH setup and productivity tools for development

## Repo

### 1. Clone

Clone this repo on `~/.dotfiles` path:

```bash
git clone https://github.com/deinsoftware/dotfiles.git ~/.dotfiles
```

### 2. Setup

On `.zshrc` file add.

```bash
# Helpers
export WINHOME=$(wslpath "$(wslvar USERPROFILE)")
export OPEN="wslview" #wsl2
export BROWSER="${OPEN}" #wsl2

export PATH="$HOME/.dotfiles/helpers/android/:$PATH"
export PATH="$HOME/.dotfiles/helpers/b64/:$PATH"
export PATH="$HOME/.dotfiles/helpers/code/:$PATH"
export PATH="$HOME/.dotfiles/helpers/md/:$PATH"
export PATH="$HOME/.dotfiles/helpers/open/:$PATH"
export PATH="$HOME/.dotfiles/helpers/search/:$PATH"
export PATH="$HOME/.dotfiles/helpers/terminal/:$PATH"
chmod +x ~/.dotfiles/helpers/**/* ~/.dotfiles/helpers/**/.[!.]*

# Custom
[ -f ~/.dotfiles/.aliases ] && . ~/.dotfiles/.aliases
[ -f ~/.dotfiles/.configs ] && . ~/.dotfiles/.configs
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
    ├── helpers
    │   ├── android
    │   ├── b64
    │   ├── code
    │   ├── md
    │   ├── open
    │   ├── search
    │   └── terminal
    ├── .aliases
    ├── .colors
    ├── .configs
    └── .hooks
```

|Name          |Description                                                                                |
|--------------|-------------------------------------------------------------------------------------------|
|`.zshrc`      | ZSH source file                                                                           |
|`helpers`     | Folder with custom helper functions to use as terminal commands                           |
| ── `android` | Helper commands for Android tools                                                         |
| ── `b64`     | Helper commands for file conversions to/from base64                                       |
| ── `code`    | Helper commands to open VSCode                                                            |
| ── `open`    | Helper commands to open file/folder on the File Explorer or open files/url on the Browser |
| ── `search`  | Helper commands to search text inside files                                               |
| ── `terminal`| Helper commands to talk with the OS                                                       |
|`.aliases`    | File for aliases definitions                                                              |
|`.colors`     | File with terminal colors to use in other scripts                                         |
|`.configs`    | File for global configuratins.                                                            |
|`.hooks`      | ZSH hooks file with custom functions to run as validation before and after run commands   |

## Plugins

**Oh My zsh!** have [a lot of plugins](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins) to use. It's recommended to explore the options and use what is good for your needs.

> If you are using **NVM** take care of following this [configuration to avoid slowing the zsh start-up](https://lakur.tech/2021/12/10/fix-slow-zsh-startup-nvm/) and this [configuration to speed up the compinit](https://gist.github.com/ctechols/ca1035271ad134841284?permalink_comment_id=3365691)

### Official

* [adb](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/adb)
* [brew](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/brew)
* [command-not-found](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/command-not-found)
* [docker](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/docker)
* [git](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/git)
* [git-lfs](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/git-lfs)
* [github](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/github)
* [gitignore](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/gitignore)
* [history-substring-search](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/history-substring-search)
* [node](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/node)
* [npm](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/npm)
* [nvm](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/nvm)
* [vscode](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/vscode)
* [sudo](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/sudo)
* [web-search](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/web-search)
* [z](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/z)

### Extras

* [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
* [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
* [OhMyZsh-full-autoupdate](https://github.com/Pilaton/OhMyZsh-full-autoupdate)

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/Pilaton/OhMyZsh-full-autoupdate.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/ohmyzsh-full-autoupdate
```

Edit the `~/.zshrc` file and add it inside the `plugins` property (don't use commas as separators).

```diff
+ZSH_HIGHLIGHT_HIGHLIGHTERS=(main brackets pattern cursor root line)
+ZSH_HIGHLIGHT_PATTERNS=('rm -rf *' 'fg=white,bold,bg=red')

plugins=(
    ...
+   zsh-autosuggestions
+   zsh-syntax-highlighting
+   ohmyzsh-full-autoupdate
)
```

## Article Series

* [iTerm2 + Oh My Zsh! + Powerlevel10K best terminal combination for Geeks!](https://dev.to/equiman/iterm2--oh-my-zsh--powerlevel9k-best-terminal-combination-for-geeks-58l5)
* [Why Oh My ZSH is so cool?](https://dev.to/equiman/why-oh-my-zsh-is-so-cool-31gd)
* [Useful Alias for ZSH](https://dev.to/equiman/useful-alias-for-zsh-1j8b)
* [Reveal the command behind an alias with ZSH](https://dev.to/equiman/reveal-the-command-behind-an-alias-with-zsh-4d96)
* [Command validations with ZSH](https://dev.to/equiman/command-validations-with-zsh-2boa)
* [Open File Explorer and Browser from ZSH](https://dev.to/equiman/open-file-explorer-and-browser-mbb)
* [ZSH cheatsheet for git plugin](https://dev.to/equiman/zsh-cheatsheet-for-git-plugin-1f6a)

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
