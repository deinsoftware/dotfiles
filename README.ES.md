# Configuración de ZSH

Idiomas: [🇺🇸] [English](README.md) - [🇪🇸] [Español](README.ES.md)

Configuración de ZSH y herramientas de productividad para desarrolladores

## Repo

### 1. Clonar

En la ruta `~` (home) clonar este repositorio

```bash
git init
git remote add origin https://github.com/deinacademy/zsh-setup.git
git pull origin main
```

### 2. Configurar

En el archivo `.zshrc` adicionar.

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

export GIT_USER_NAME="user" # usuario privado negocio/trabajo
export GIT_USER_EMAIL="user@mail.com" # e-mail privado negocio/trabajo
export GITHUB_USER_NAME="user" # usuario publico personal 
export GITHUB_USER_EMAIL="user@users.noreply.github.com" # e-mail publico personal 
[ -f ~/.aliases ] && . ~/.aliases
[ -f ~/.colors ] && . ~/.colors
[ -f ~/.hooks ] && . ~/.hooks
```

> Las constante `OPEN` y `BROWSE` necesitan ser configuradas de acuerdo al SO que se este usando. Windows (WSL2) y macOS usan el mismo comando para abrir el explorador de archivos como el navegador por defecto, en Ubuntu (Linux) se debe especificar cada uno por separado.

|SO|`OPEN`|`BROWSER`|
|---|---|---|
|Windows (WSL2)|`"explorer.exe"`|`"${OPEN}"`|
|macOS|`"open"`|`"${OPEN}"`|
|Ubuntu|`"xdg-open"`, `"gnome-open"`, `"nautilus"` ...|`"googlechrome"`, `"firefox"` ...|

### 3. Permisos

Ahora adicione permisos de ejecución a los scripts de los `Helpers`:

```bash
chmod +x ~/.helpers/**/*
```

### 4. Actualizar

Una vez termine, guarde el archivo `.zshrc`, cierre y reabra todas las terminales o actualice el archivo fuente ejecutando el comando `source ~/.zshrc`.

¡Eso es todo amigxs! Ya quedó listo para ser usado.

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

## Serie de Articulo (en Inglés)

- [Useful Alias for ZSH](https://dev.to/equiman/useful-alias-for-zsh-1j8b)
- [Reveal the command behind an alias with ZSH](https://dev.to/equiman/reveal-the-command-behind-an-alias-with-zsh-4d96)
- [Command validations with ZSH](https://dev.to/equiman/command-validations-with-zsh-2boa)
- [Open File Explorer and Browser from ZSH](https://dev.to/equiman/open-file-explorer-and-browser-mbb)
- [Automatic change directory after git clone](https://dev.to/equiman/automatic-change-directory-after-git-clone-8ei)
- [ZSH cheatsheet for git plugin](https://dev.to/equiman/zsh-cheatsheet-for-git-plugin-1f6a)
- [base64 encode/decode multiple files](https://dev.to/equiman/base64-encode-decode-multiple-files-2ol1)
