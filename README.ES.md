# Configuración de ZSH

Idiomas: [[EN]](README.md) - [[ES]](README.ES.md)

## Repo

En la ruta `~` (home) clonar este repositorio

```bash
git init
git remote add origin https://github.com/deinacademy/zsh-setup.git
git pull origin main
```

En el archivo `.zshrc` adicionar.

```bash
# Helpers
export OPEN="explorer.exe"
export PATH="$HOME/.helpers/b64/:$PATH"
export PATH="$HOME/.helpers/git/:$PATH"
export PATH="$HOME/.helpers/md/:$PATH"
export PATH="$HOME/.helpers/open/:$PATH"
chmod +x ~/.helpers/**/*

# Custom
local WINHOME=$(wslpath "$(wslvar USERPROFILE)")

local GIT_USER_NAME="user" # usuario privado negocio/trabajo
local GIT_USER_EMAIL="user@mail.com" # e-mail privado negocio/trabajo
local GITHUB_USER_NAME="user" # usuario publico personal 
local GITHUB_USER_EMAIL="user@users.noreply.github.com" # e-mail publico personal 
[ -f ~/.aliases ] && . ~/.aliases
[ -f ~/.colors ] && . ~/.colors
[ -f ~/.hooks ] && . ~/.hooks
```

Adicionr permisos de ejecución a los scripts de los `Helpers`:

```bash
chmod +x ~/.helpers/**/*
```

Una vez termine, cierre y abra todas las terminales o actualice el archivo fuente ejecutando el comando `source ~/.zshrc` y ya queda listo para ser usado.

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
|`.cheatsheet`| Carpeta con archivos de markdown para ver el pastel de los comandos de los `helpers` y commando `alias`|
|`.helpers`| Carpeta con las funciones `helper` (ayudantes) para usar como comandos en la terminal |
|`.aliases`| Archivo con la definición de los alias |
|`.colors`| Archivo con colores de terminal para usar en otros scripts |
|`.hooks`| Archivo con hooks de ZSH con funciones que corren antes o después de ejecutar algún comando en la terminal |
|`.zshrc`| Archivo fuente de ZSH |

## Serie de Articulo (in Inglés)

- [Reveal the command behind an alias with ZSH](https://dev.to/equiman/reveal-the-command-behind-an-alias-with-zsh-4d96)
- [Useful Alias for ZSH](https://dev.to/equiman/useful-alias-for-zsh-1j8b)
- [Automatic change directory after git clone](https://dev.to/equiman/automatic-change-directory-after-git-clone-8ei)
- [Command validations with ZSH](https://dev.to/equiman/command-validations-with-zsh-2boa)
- [Open File Explorer and Browser from ZSH](https://dev.to/equiman/open-file-explorer-and-browser-mbb)
- [ZSH cheatsheet for git plugin](https://dev.to/equiman/zsh-cheatsheet-for-git-plugin-1f6a)
- [base64 encode/decode multiple files](https://dev.to/equiman/base64-encode-decode-multiple-files-2ol1)
