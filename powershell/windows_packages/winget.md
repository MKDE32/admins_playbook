# Winget Cheat Sheet (Admin / IT)

## 🔹 Basic commands

winget --version
→ Check installed winget version

winget search <app>
→ Search for an application

winget show <app>
→ Show details about a package

winget info <app>
→ Extended info (publisher, license, etc.)

## 🔹 Install applications

winget install <app>
→ Install latest version

winget install <app> --silent
→ Silent install (no UI prompts)

winget install <app> --accept-source-agreements --accept-package-agreements
→ Fully automated install (scripts)

winget install <app> --scope machine
→ Install for all users (admin required)

## 🔹 Uninstall applications

winget uninstall <app>
→ Remove application

winget uninstall <app> --silent
→ Silent uninstall

## 🔹 Upgrade applications

winget upgrade
→ List upgradable apps

winget upgrade <app>
→ Upgrade specific app

winget upgrade --all
→ Upgrade all installed apps

winget upgrade --all --silent
→ Fully automated system update (admin scripts)

## 🔹 List installed apps

winget list
→ Show all installed packages

winget list <app>
→ Filter specific app

## 🔹 Export / Import (important for admins)

winget export -o apps.json
→ Export installed apps list

winget import -i apps.json
→ Reinstall environment from file

## 🔹 Sources

winget source list
→ Show repositories

winget source update
→ Refresh package sources

winget source reset --force
→ Reset broken sources

## 🔹 Logging / troubleshooting

winget --verbose
→ Detailed output

winget install <app> --verbose-logs
→ Full log output for debugging

## 🔹 Useful admin automation examples

winget upgrade --all --silent --accept-package-agreements --accept-source-agreements
→ Fully automated patching run

winget install vscode git python --silent
→ Mass install dev tools

winget list | findstr /i "chrome"
→ Check if app is installed

## ⚠️ Notes for admins

* Run terminal as Administrator for system-wide installs
* Not all apps support silent install
* Some packages require MS Store backend
* Winget is best for:

  * baseline system setup
  * dev environments
  * patch automation
