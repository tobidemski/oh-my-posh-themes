# oh-my-posh-themes

## General

### oh-my-posh setup
1. Download & install
Set-ExecutionPolicy Bypass -Scope Process -Force; Invoke-Expression ((New-Object System.Net.WebClient).DownloadString('https://ohmyposh.dev/install.ps1'))

2. Configure your theme
Located themes: $env:POSH_THEMES_PATH

3. Nerd Font hinzufügen (als Admin ausführen)
oh-my-posh font install

3. Powershell 5.1 Profile erstellen
5.1 (eins von beiden wählen - RECOMMENDED: 2. Option da ISE kein oh-my-posh kann)
  - (ALLE PS Instanzen) Pfad: C:\Users\<USER>\Documents\WindowsPowerShell\Profile.ps1
  - (Exclude ISE Instanzen) Pfad: C:\Users\<USER>\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1

7.X Pfad: C:\Users\<USER>\Documents\PowerShell\Profile.ps1

4. Beide Profile mit oh-my-posh Start Command erweitern
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH/custom/darkblood-extend.omp.json" | Invoke-Expression

5. Terminal-Icons installieren für Dictionary icons (basiert auf Nerd Fonts)
Install-Module -Name Terminal-Icons -Repository PSGallery

6. Termin-Icons über das PS-Profil importieren
Import-Module -Name Terminal-Icons

### Suggestions and History

***Step 1 & 2 können für Powershell 7 übersprungen werden da die erforderliche Version bereits installiert ist.***

1. Install PowershellGet as a module (To get the -AllowPrerelease parameter flag available) (-Force to side-by-side install because system shipped version 1.0.0.1)
Install-Module PowerShellGet -Force

2. PSReadLine für suggestions
Install-Module -Name PSReadLine -AllowPrerelease -Force (-Force to side-by-side install because system shipped version 2.0.0)

3. Powershell Profile erweitern
Import-Module PSReadLine
Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView
Set-PSReadLineOption -EditMode Windows
Set-PSReadLineKeyHandler -Key UpArrow -Function HistorySearchBackward
Set-PSReadLineKeyHandler -Key DownArrow -Function HistorySearchForward
