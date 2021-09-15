# CHEATSHEET OPEN AND BROWSE

## File Explorer

|Alias|Command|Description|
|---|---|---|
|`o`|`open_p -p .`|Open current path on file explorer or finder|
|`o <path>`|`open_p -p <path>`|Open a relative or absolute path on file explorer or finder|

## Browser

|Alias|Command|Description|
|---|---|---|
|`b`|`open_browser -f ./index.htm`|Open a browser with `index.html` on current path|
|`bu <url>`|`open_browser -u <url>`|Open a browser with specified URL|

## React/Web

|Alias|Command|Description|
|---|---|---|
|`obf`|`open_path -p build`|Open `.\build` folder inside current path on file explorer or finder|
|`obc`|`open_path -p coverage`|Open `.\coverage` folder inside current path on file explorer or finder|
|`bcr`|`open_browser -f coverage`|Open coverage `.\coverage\lcov-report\index.html` report on Browser|
|`blh`|`open_browser -u http://localhost`|Open a browser as `localhost`|
|`blhp <port>`|`open_browser -u http://localhost:<port>`|Open a browser as `localhost` on specific `port`|

## GitHub

|Alias|Command|Description|
|---|---|---|
|`bgr`|`open_git_repo`|Browse the current GitHub repo url|
|`bgb`|`open_git_branch`|Browse the current GitHub current Branch url|
|`bgp`|`open_git_pull`|Browse the current GitHub Pull Request url|
|`bgc [<branch>]`|`open_git_compare [<branch>]`|Browse the compare current branch with another base branch [`dev` by default] |

> Works with repositories cloned with HTTP or SSH

## NPM

|Alias|Command|Description|
|---|---|---|
|`bnp`|`open_npm_package`| Browse the NPM package on `package.json`|
|`bnc`|`open_npm_clipboard`|Browse the NPM package on browser searching by name on clipboard|
