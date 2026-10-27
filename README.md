# Aculeus desktop releases

Installers for the Aculeus desktop app.

## Install

Run one command. It downloads the installer for your computer from the
[latest release](https://github.com/Aculeus-inc/aculeus-desktop-releases/releases/latest),
installs Aculeus and opens it.

- macOS or Linux, in Terminal:

  ```sh
  curl -fsSL https://github.com/Aculeus-inc/aculeus-desktop-releases/releases/latest/download/install.sh | sh
  ```

- Windows, in PowerShell:

  ```powershell
  irm https://github.com/Aculeus-inc/aculeus-desktop-releases/releases/latest/download/install.ps1 | iex
  ```

On a Mac it picks the Apple silicon or Intel build and installs Aculeus in
Applications (or `~/Applications` without administrator rights); installed this
way, macOS does not ask you to approve the unsigned app. On Debian and Ubuntu it
installs the `.deb` with apt, which asks for your password, and on other Linux
systems it puts the AppImage in `~/Applications`. On Windows it installs Aculeus
for your user account.

The Windows and Linux apps update themselves from this page: they check when they
start and every ten minutes, download a new release in the background and offer to
restart into it. macOS installs only signed updates, so until the app is signed,
run the command again for each new release.

The app runs the Aculeus harness, which gives it its agents, commands, skills
and permission rules. Aculeus builders install the harness from its repository
first (`install/install.sh`, or `install\install.ps1` on Windows). Without it the
app explains how to install it. Prompts go only to a provider you connect.

## Updating the harness

The desktop update installs the app and its bundled document and Chrome tools.
Agents, skills, provider presets and client overlays live in the separate harness
checkout. In that checkout, run `git pull --ff-only`, rerun `install/install.ps1`
on Windows or `install/install.sh` on macOS/Linux, and restart Aculeus. Keep your
client settings in their existing overlays. This step adds the Inference.net
preset and the latest document/browser instructions for older harness installs.

## Download a file instead

| Computer | File |
|---|---|
| Mac with Apple silicon | `aculeus-desktop-mac-arm64.dmg` |
| Intel Mac | `aculeus-desktop-mac-x64.dmg` |
| Windows | `aculeus-desktop-win-x64.exe` |
| Linux | `aculeus-desktop-linux-x86_64.AppImage`, or `aculeus-desktop-linux-amd64.deb` for Debian and Ubuntu |

These installers are unsigned for now, so approve the app once:

- macOS: open the `.dmg` and drag Aculeus to Applications. The first time it
  opens, macOS says it cannot verify the app; open System Settings, Privacy &
  Security, and click Open Anyway.
- Windows: run the `.exe`. If SmartScreen says "Windows protected your PC", click
  More info, then Run anyway.
- Linux: make the AppImage executable and run it, or install the `.deb` with
  `sudo apt install ./aculeus-desktop-linux-amd64.deb`.

The other files in each release are what the commands and the apps read:
`install.sh` and `install.ps1` are the commands' scripts, and `latest.yml`,
`latest-linux.yml` and the `.blockmap` tell the apps about updates.

## Notices

The Aculeus desktop app is built from [OpenCode](https://github.com/anomalyco/opencode)
Desktop. Aculeus is not built by, affiliated with or endorsed by the OpenCode
project. OpenCode's license:

```
MIT License

Copyright (c) 2025 opencode

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

The app carries this notice (`LICENSE.opencode.txt` in its resources) and the
SIL Open Font License for its Manrope font; the Windows and Linux apps also carry
Electron's and Chromium's licenses (`LICENSE.electron.txt`,
`LICENSES.chromium.html`). The Aculeus name, mark and wordmark belong to
Aculeus, Inc. and are not covered by these licenses.
