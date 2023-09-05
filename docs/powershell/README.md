# PowerShell

Useful alias to use on PowerShell side to deal with `WSL`.

```powershell
# Alias
function getAliases() {
    echo "(Get-Alias).DisplayName"
    (Get-Alias).DisplayName
}
Set-Alias a -value getAliases

# Profile
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
