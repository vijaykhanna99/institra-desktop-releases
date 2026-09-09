# Institra Desktop releases

Installers and update feeds for **Institra Desktop**, the secure exam client
for [Institra](https://institra.in). This repository holds release assets
only; no source code lives here.

Asset names carry no version, so the links below always resolve to the
current release. The version you are installing is in the release title, in
`SHA256SUMS.txt`, and — once installed — in `dpkg -l institra-desktop`.

| Platform | Download | Notes |
|---|---|---|
| Ubuntu 24.04+ | [`institra-desktop-amd64.deb`](https://institra.in/download/ubuntu) | Preferred. `sudo apt install ./institra-desktop-amd64.deb` |
| Ubuntu 24.04+ | [`institra-desktop-x86_64.AppImage`](https://institra.in/download/appimage) | Needs `sudo apt install libfuse2` |
| macOS 13+ | — | On request while the build is unnotarised |
| Windows 10/11 | — | On request while the installer is unsigned |

Verify before you install — these packages are signed by no Debian, Ubuntu
or Apple key, so the checksum is the only thing vouching for them:

```
curl -fL -o institra-desktop-amd64.deb https://institra.in/download/ubuntu
curl -fL -o SHA256SUMS.txt https://institra.in/download/checksums
sha256sum --ignore-missing -c SHA256SUMS.txt
```

Ubuntu's default Wayland session does not let any application hold the
keyboard, so app switching is recorded rather than blocked, and no
application can block screen capture there. The client reports what it
actually enforced and your professor sees the same reading.
[What it does on Ubuntu, exactly](https://institra.in/desktop#download).

Installed clients check this repository for updates while idle and never
during an exam. Students: your institute tells you which version to use;
when in doubt install the latest release.
