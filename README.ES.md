# ZSH Dev Toolkit

Idiomas: [🇺🇸] [English](README.md) - [🇪🇸] [Español](README.ES.md)

Configuración de ZSH y herramientas de productividad para desarrollo

## Repo

### 1. Clonar

En la ruta `~` (home) clonar este repositorio

```bash
git init
git remote add origin https://github.com/deinsoftware/zsh-dev-toolkit.git
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
export PATH="$HOME/.helpers/code/:$PATH"
export PATH="$HOME/.helpers/md/:$PATH"
export PATH="$HOME/.helpers/open/:$PATH"
export PATH="$HOME/.helpers/os/:$PATH"
export PATH="$HOME/.helpers/search/:$PATH"
export PATH="$HOME/.helpers/terminal/:$PATH"
chmod +x ~/.helpers/**/*

# Custom
[ -f ~/.aliases ] && . ~/.aliases
[ -f ~/.colors ] && . ~/.colors
[ -f ~/.hooks ] && . ~/.hooks
```

> Las constantes `OPEN` y `BROWSE` necesitan ser configuradas de acuerdo al SO que se este usando. Windows (WSL2) y macOS usan el mismo comando para abrir el explorador de archivos como el navegador por defecto, en Ubuntu (Linux) se debe especificar cada uno por separado.

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

### 5. Extra

Una lista útil de alias de PowerShell para lidiar con `WSL`.

```powershell
# Alias
function getAliases() {
    echo "(Get-Alias).DisplayName"
    (Get-Alias).DisplayName
}
Set-Alias a -value getAliases

# Perfil
function checkIfProfileExist() {
    echo "Test-Path $PROFILE"
    Test-Path $PROFILE
}
Set-Alias pe -value checkIfProfileExist

function createProfile() {
    echo "New-Item -path $PROFILE -type file -force"
    New-Item -path $PROFILE -type file -force
}
Set-Alias pc -value createProfile

function editProfile() {
    echo "code $PROFILE"
    code $PROFILE
}
Set-Alias e -value editProfile

function reloadProfile() {
    echo ". $PROFILE"
    . $PROFILE
}
Set-Alias r -value reloadProfile

# WSL
function editWslConfig() {
    echo "code $HOME/.wslconfig"
    code $HOME/.wslconfig
}
Set-Alias wc -value editWslConfig

function wslShutdown() {
    echo "wsl --shutdown"
    wsl --shutdown
}
Set-Alias ws -value wslShutdown

function wslList() {
    echo "wsl -l -v"
    wsl -l -v
}
Set-Alias wl -value wslList

function wslRun() {
    echo "wsl"
    wsl
}
Set-Alias wr -value wslRun

function wslRunUbuntu() {
    echo "wsl --distribution Ubuntu"
    wsl --distribution Ubuntu
}
Set-Alias wru -value wslRunUbuntu

function wslStatus() {
    echo "wsl --status"
    wsl --status
}
Set-Alias wst -value wslStatus
```

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
│   └── search
├── .aliases
├── .colors
├── .hooks
└── .zshrc
```

|Name|Description|
|---|---|
|`.cheatsheet`| Carpeta con archivos de markdown para ver el pastel de los comandos de los `helpers` y commando `alias`|
|`.helpers`| Carpeta con las funciones `helper` (ayudantes) para usar como comandos en la terminal |
| ── `b64`| Comandos para la conversion de archivos desde/hacia base64 |
| ── `git`| Comandos para clonar repositorios de git con opciones extra (TEP) |
| ── `md`| Comandos para ver archivos MarkDown en la terminal (TEP) |
| ── `open`| Commandos para abrir archivos/rutas en el Explorador de Archivos o abrir archivos/url en el Navegador |
| ── `search`| Comandos para buscar textos en los archivos |
|`.aliases`| Archivo con la definición de los alias |
|`.colors`| Archivo con colores de terminal para usar en otros scripts |
|`.hooks`| Archivo con hooks de ZSH con funciones que corren antes o después de ejecutar algún comando en la terminal |
|`.zshrc`| Archivo fuente de ZSH |

## ZSH plugins

Hay un montón de [plugins para ZSH](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins), estos son los mas útiles que he encontrado.

### Oficiales

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

## Serie de Articulo

Inglés:

* [Useful Alias for ZSH](https://dev.to/equiman/useful-alias-for-zsh-1j8b)
* [Reveal the command behind an alias with ZSH](https://dev.to/equiman/reveal-the-command-behind-an-alias-with-zsh-4d96)
* [Command validations with ZSH](https://dev.to/equiman/command-validations-with-zsh-2boa)
* [Open File Explorer and Browser from ZSH](https://dev.to/equiman/open-file-explorer-and-browser-mbb)
* [ZSH cheatsheet for git plugin](https://dev.to/equiman/zsh-cheatsheet-for-git-plugin-1f6a)
* [base64 encode/decode multiple files](https://dev.to/equiman/base64-encode-decode-multiple-files-2ol1)

Español:

* [Mover el Sistema de Archivos de WSL a otro disco](https://dev.to/equimancho/mover-el-sistema-de-archivos-de-wsl-a-otro-disco-3fbi)

---

## Acerca

### Construido

*-* [VS Code](https://code.visualstudio.com/) - Edición de código re-definida.
*-* [Widows Terminal](https://github.com/Microsoft/Terminal/) - Una aplicación de terminal moderna para usuarios de la línea de comandos.

### Versionamiento

Usamos [SemVer](https://semver.org/lang/es/) para el versionamiento. Para las versiones disponible, vaya a [ZSH Dev Toolkit](https://github.com/deinsoftware/zsh-dev-toolkit/tags) en GitHub.

### Authors

* **Camilo Martinez** [[Equiman](http://stackoverflow.com/story/equiman)]

También puede ver la lista de los [contribuyentes](https://github.com/deinsoftware/zsh-dev-toolkit/contributors) que han participado en este proyecto.

### Patrocinadores

Si este proyecto te ayudó, por favor considera invitarme a un café.

[![GitHub Sponsors](https://img.shields.io/badge/-GitHub%20Sponsors-gray?style=flat&labelColor=171515&logo=github&logoColor=white&link=https://github.com/sponsors/deinsoftware)](https://github.com/sponsors/deinsoftware)
[![paypal](https://img.shields.io/badge/-PayPal-gray?style=flat&labelColor=00457C&logo=paypal&logoColor=white&link=https://paypal.me/equiman/3)](https://paypal.me/equiman/3)

### Licencia

Este proyecto esta licenciado bajo la Licencia MIT - vea [LICENCIA](LICENSE.md) para mas detalles.
