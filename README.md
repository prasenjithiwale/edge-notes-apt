# Edge Notes APT repository

Signed Debian packages of [Edge Notes](https://github.com/prasenjithiwale/edge-notes),
a notes widget docked to the edge of your screen. Published automatically by the
Edge Notes release workflow; nothing here is edited by hand.

## Install (Debian, Ubuntu, Kubuntu and derivatives, x86_64)

```bash
sudo install -d -m 0755 /etc/apt/keyrings
curl -fsSL https://prasenjithiwale.github.io/edge-notes-apt/key.gpg | sudo gpg --dearmor -o /etc/apt/keyrings/edge-notes.gpg
echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/edge-notes.gpg] https://prasenjithiwale.github.io/edge-notes-apt stable main" \
  | sudo tee /etc/apt/sources.list.d/edge-notes.list
sudo apt update
sudo apt install edge-notes
```

New versions then arrive with `sudo apt update && sudo apt upgrade`.

Needs Ubuntu 22.04 or newer (or Debian 12 or newer); `libappindicator3-1` comes
from Ubuntu's universe component.

## Remove

```bash
sudo apt remove edge-notes
sudo rm /etc/apt/sources.list.d/edge-notes.list /etc/apt/keyrings/edge-notes.gpg
```

## Signing key

`Edge Notes APT repository`, RSA 4096, fingerprint:

    BA717EAAFC819ABAB0ED6B517A4EFAFF5DAC007C

`apt` checks every download against it.
