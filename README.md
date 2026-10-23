# Aculeus desktop releases

Installers for the Aculeus desktop app. Download the file for your computer from
the [latest release](https://github.com/Aculeus-inc/aculeus-desktop-releases/releases/latest):

| Computer | File |
|---|---|
| Mac with Apple silicon | `aculeus-desktop-mac-arm64.dmg` |
| Intel Mac | `aculeus-desktop-mac-x64.dmg` |
| Windows | `aculeus-desktop-win-x64.exe` |
| Linux | `aculeus-desktop-linux-x86_64.AppImage`, or `aculeus-desktop-linux-amd64.deb` for Debian and Ubuntu |

The installers are unsigned for now, so approve the app once:

- macOS: open the `.dmg` and drag Aculeus to Applications. The first time it
  opens, macOS says it cannot verify the app; open System Settings, Privacy &
  Security, and click Open Anyway.
- Windows: run the `.exe`. If SmartScreen says "Windows protected your PC", click
  More info, then Run anyway.
- Linux: make the AppImage executable and run it, or install the `.deb` with
  `sudo apt install ./aculeus-desktop-linux-amd64.deb`.

The Windows and Linux apps update themselves from this page: they check when they
start and every ten minutes, download a new release in the background and offer to
restart into it. macOS installs only signed updates, so until the app is signed,
download each new `.dmg` and drag Aculeus over the old app.

The other files in each release (`latest.yml`, `latest-linux.yml` and the
`.blockmap`) are what the apps read to update; you do not need them.

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
