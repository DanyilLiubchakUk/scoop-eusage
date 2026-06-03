# eUsage Scoop Bucket

Public Scoop bucket for eUsage Windows installs.

## Install Scoop

Run PowerShell as your normal user:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
irm get.scoop.sh | iex
```

## Install eUsage

```powershell
scoop bucket add eusage https://github.com/DanyilLiubchakUk/scoop-eusage
scoop install eusage
```

The manifest runs `Unblock-File` on the downloaded installer before silent install. Windows may still show SmartScreen because the free build is unsigned.

If Windows still blocks the installer, run:

```powershell
Unblock-File "$env:USERPROFILE\scoop\cache\eusage#0.6.24#*.exe"
scoop install eusage
```

If SmartScreen appears, choose `More info`, then `Run anyway`.

## Release updates

`bucket/eusage.json` is updated automatically by the `DanyilLiubchakUk/eusage`
publish workflow after each release tag. Manual edits are only for recovery if
that workflow fails.

## Upgrade

The app normally updates itself through GitHub Releases and the in-app `Restart to update` button.

Use Scoop only if reinstall or recovery is needed:

```powershell
scoop update
scoop update eusage
```
