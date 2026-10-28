# flowSIGHT releases

flowSIGHT releases for Linux on x86-64. The source lives in a private repository. This repository holds only what an install downloads: each release's installer, its offline tarball and their checksums.

## Install

Run this as root on a Linux host with Docker Engine 24+ and the Compose plugin:

```sh
curl -fsSL https://github.com/interroseclabs/flowsight-releases/releases/latest/download/install.sh | sudo bash
```

Or with wget:

```sh
wget -qO- https://github.com/interroseclabs/flowsight-releases/releases/latest/download/install.sh | sudo bash
```

The installer:
- installs into `/opt/flowsight`;
- generates every secret, kept in a `.env` readable by root only;
- pulls the images and starts flowSIGHT;
- ends with `Open http://<host>:3000 to activate flowSIGHT`.

That page pairs the install with your Interrosec account.

For a specific version, use that release's own link: `https://github.com/interroseclabs/flowsight-releases/releases/download/vX.Y.Z/install.sh`.

## Upgrade

Run the same command again. It upgrades the existing install where it is, and keeps its settings, secrets and data. After that, an admin can install later releases from Settings → Updates.

## Offline install

Download `flowsight-X.Y.Z.tar.gz` from a release, then:

```sh
tar xzf flowsight-X.Y.Z.tar.gz
cd flowsight
sudo ./install.sh
```

## Each release

| File | What it is |
|---|---|
| `install.sh` | The online installer, pinned to this release |
| `flowsight-X.Y.Z.tar.gz` | The offline install: compose file, installer and every image |
| `SHA256SUMS` | SHA-256 of the two files above |

## Requirements

- Linux on x86-64 (Ubuntu 22.04+ or RHEL 8+ recommended)
- Docker Engine 24+ with the Compose plugin
- 8 GB RAM minimum (16 GB recommended)
- 50 GB disk (SSD recommended)
