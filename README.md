# ZSH setup

## Repo

On `~` (home) path clone this repo

```bash
git init 
git remote add origin https://github.com/deinacademy/zsh-setup.git
git pull origin main
```

On `.zshrc` file add.

```bash
# Helpers
export PATH="$HOME/.helpers/b64/:$PATH"
export PATH="$HOME/.helpers/git/:$PATH"
local OPEN="explorer.exe"
export PATH="$HOME/.helpers/open/:$PATH"

# Custom
local WINHOME=$(wslpath "$(wslvar USERPROFILE)")

local GIT_USER_NAME="user"
local GIT_USER_EMAIL="user@mail.com"
local GITHUB_USER_NAME="user"
local GITHUB_USER_EMAIL="user@users.noreply.github.com"
if [ -f ~/.aliases ]; then
. ~/.aliases
fi

if [ -f ~/.hooks ]; then
. ~/.hooks
fi
```

Once finish, reopen all terminals or update his source running `source ~/.zshrc` command and now you can use it.

## Article Series

- [Reveal the command behind an alias with ZSH](https://dev.to/equiman/reveal-the-command-behind-an-alias-with-zsh-4d96)
- [Useful Alias for ZSH](https://dev.to/equiman/useful-alias-for-zsh-1j8b)
- [Automatic change directory after git clone](https://dev.to/equiman/automatic-change-directory-after-git-clone-8ei)
- [Command validations with ZSH](https://dev.to/equiman/command-validations-with-zsh-2boa)
- [Open File Explorer and Browser from ZSH](https://dev.to/equiman/open-file-explorer-and-browser-mbb)
- [ZSH cheatsheet for git plugin](https://dev.to/equiman/zsh-cheatsheet-for-git-plugin-1f6a)
- [base64 encode/decode multiple files](https://dev.to/equiman/base64-encode-decode-multiple-files-2ol1)
