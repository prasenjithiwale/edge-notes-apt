# Ledge downloads

Packages of [Ledge](https://github.com/prasenjithiwale/edge-notes), a notes,
tasks and focus widget docked to the edge of your screen — for macOS, Windows,
Debian and Ubuntu.

**The downloads, with install instructions for each platform, are on the site
this repository serves: <https://prasenjithiwale.github.io/edge-notes-apt/>**

This repository is the publishing target, not the source. It holds the packages,
a signed APT index, the public key and a generated landing page; it is written by
the release workflow in the source repository, and nothing in it is edited by
hand. An edit made here is overwritten by the next release.

## apt, in short

```bash
sudo install -d -m 0755 /etc/apt/keyrings
curl -fsSL https://prasenjithiwale.github.io/edge-notes-apt/key.gpg | sudo gpg --dearmor -o /etc/apt/keyrings/ledge.gpg
echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/ledge.gpg] https://prasenjithiwale.github.io/edge-notes-apt stable main" \
  | sudo tee /etc/apt/sources.list.d/ledge.list
sudo apt update
sudo apt install ledge
```

Debian 12+, Ubuntu 22.04+, x86_64. New versions then arrive with
`sudo apt update && sudo apt upgrade`. To remove it:
`sudo apt remove ledge`, then
`sudo rm /etc/apt/sources.list.d/ledge.list /etc/apt/keyrings/ledge.gpg`.

## What is where

| Path | What |
|---|---|
| `index.html` | The landing page, generated on every release |
| `screenshots/` | The pictures on that page |
| `pool/`, `dists/` | The Debian packages and the signed index |
| `macos/` | The `.dmg`, with `SHA256SUMS` |
| `windows/` | The `.exe` and `.msi`, with `SHA256SUMS` |
| `key.gpg` | The public half of the APT signing key |

Older versions of every package are kept.
