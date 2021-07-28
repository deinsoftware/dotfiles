# zsh-setup

File: `.zshrc`

```
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
