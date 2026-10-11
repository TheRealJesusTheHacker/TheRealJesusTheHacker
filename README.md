# Skyler — @JesusTheHacker

I run **Sentinel Safeguard LLC** — cybersecurity, penetration testing, and IT.
I do the work myself, and I build the tools I use on the job. Everything below
is open-source and free.

- [⚡ NitroCore](#-nitrocore--windows-system-optimizer) — Windows system optimizer
- [🗜️ VectorZip](#️-vectorzip--lossless-file-compressor) — lossless file compressor
- [🐕 ShibaCuddles](#-shibacuddles--network-scanner--security-testing-suite) — network scanner & security testing suite
- [🔥 Hellhound.exe](#-hellhoundexe--ransomware-kill-chain-simulator) — ransomware kill-chain visual simulator
- [🐶 JadeOS](#-jadeos--pentesting-linux-distro) — security & pentesting Linux distro
  - _Hint: #OpLint-Trap 2026_

---

## ⚡ NitroCore — Windows System Optimizer

[![release](https://img.shields.io/github/v/release/TheRealJesusTheHacker/NitroCore)](https://github.com/TheRealJesusTheHacker/NitroCore/releases)

Over time Windows collects junk files, runs background programs you don't need,
and ships with settings that favor battery life over speed. NitroCore cleans the
junk, quiets the background noise, and flips the right switches — from one simple
dashboard. You don't need to know what the registry is. Pick a profile, hit a
button, let it work.

**What it does:**
- **One-click Gaming & Cybersecurity profiles** — Gaming goes aggressive for max
  FPS; Cybersecurity stays stable and keeps Windows Update patching.
- **Temp & browser cache cleanup** — clears system temp folders and Chrome/Firefox
  caches, with a before/after report of MB freed.
- **Disk cleanup** — Windows' native cleanup plus DISM component cleanup, with live
  drive-usage bars.
- **Registry tuning** — disables hibernation, sets the pagefile to automatic, trims
  visual effects for snappier windows.
- **Background service management** — Gaming trims non-essential services (Update,
  BITS, Search) to manual; Cybersecurity leaves patching alive.
- **Performance tuning** — switches to the Ultimate Performance power plan and raises
  priority on key system processes.
- **Live stats header** — CPU, RAM, disk, and power plan at a glance.

**Safety first:**
- Offers a **Windows restore point** before anything risky — create, skip, or cancel,
  your call.
- **Preview mode** shows every change it *would* make before it makes any of them.
  Nothing happens in secret.
- Your personal files are never touched. The one exception is Downloads cleanup,
  which asks first and only touches files 30+ days old.
- Full operation logs on disk. Requires admin rights — Windows won't let anything
  tune the system without them.

**Get it:** `winget install TheRealJesusTheHacker.NitroCore` — or grab the .exe from
[releases](https://github.com/TheRealJesusTheHacker/NitroCore/releases).
Windows 10/11, 64-bit. MIT.

**Who it's for:** gamers chasing FPS, security folks who need their tooling running
fast, anyone with a slow Windows box who doesn't want to hand-edit the registry.

---

## 🗜️ VectorZip — Lossless File Compressor

[![release](https://img.shields.io/github/v/release/TheRealJesusTheHacker/VectorZip)](https://github.com/TheRealJesusTheHacker/VectorZip/releases)

A completely lossless file compressor built from real compression theory: LZ77
sliding-window dictionary matching plus Huffman entropy coding. Compress anything —
documents, backups, datasets — and get back byte-identical data, every time.
Corruption is never silent: every 64 KiB chunk carries a CRC32 that is verified on
decompression, so a truncated or damaged archive fails loudly instead of quietly
handing you bad data.

**What it does:**
- **Truly lossless** — decompressing a `.vzip` file returns byte-identical data,
  verified by round-trip tests. Never "close enough."
- **Workhorse fast** — ~10 MB/s on everyday files; incompressible data (random
  bytes, zips, videos) passes through raw at ~800 MB/s and never grows the file.
- **Memory-efficient** — chunked processing keeps memory usage flat regardless of
  file size. Compress multi-gigabyte files on modest hardware.
- **Desktop GUI** — drag & drop files or whole folders, batch processing, live
  per-file progress, real statistics (original vs. output size, space saved),
  safe-by-default (originals are never overwritten), custom output folder, and a
  color-coded activity log.
- **CLI and Python API** — `vzip compress` / `vzip decompress` on the command line,
  or `compress_file` / `decompress_file` in your own code.
- **Portable** — pure Python 3.8+, no compiled extensions. Older `.vzip` formats
  (v1, v2) still decompress.

**Get it:** standalone Windows `.exe` and Linux binary from
[releases](https://github.com/TheRealJesusTheHacker/VectorZip/releases) — no Python
required. MPL-2.0.

**Who it's for:** anyone archiving backups, datasets, or documents; developers who
want a clean compression API; anyone who's been burned by silent corruption.

---

## 🐕 ShibaCuddles — Network Scanner & Security Testing Suite

[![release](https://img.shields.io/github/v/release/TheRealJesusTheHacker/ShibaCuddles)](https://github.com/TheRealJesusTheHacker/ShibaCuddles/releases)

A fast, multi-threaded network scanner with a dark PyQt6 GUI dashboard and a full
CLI. Point it at a network you own and it maps what's alive, what's open, and
what's running — then hands you the results in JSON, CSV, XML, or plain text.

**What it does:**
- **Device discovery** — ICMP ping sweep, ARP scanning, hostname resolution,
  MAC detection.
- **Port scanning** — TCP 1–65535, UDP detection, banner grabbing, service version
  detection.
- **Advanced analysis** — service fingerprinting (20+ services), TTL-based OS
  fingerprinting, vulnerability detection, real-time statistics.
- **GUI dashboard** — live results table with alive/down indicators, card-based
  stats (hosts scanned, hosts alive, open ports), color-coded activity log,
  real-time progress, multi-format export.
- **WiFi security testing** — device deauthentication (requires the `aircrack-ng`
  suite), broadcast deauth, monitor-mode control, network scanning, channel analysis.
- **Scope-gated by design** — every WiFi attack function checks its target against
  `authorized_targets.json` *before transmitting anything*. A target that isn't
  listed is refused, with no override.

**Get it:** standalone Windows `.exe` and Linux binary from
[releases](https://github.com/TheRealJesusTheHacker/ShibaCuddles/releases). MIT.

**Who it's for:** security professionals and network admins running authorized
assessments, pentesters, home-lab folks auditing their own networks. Authorized use
only — scanning or interfering with networks you don't own or lack written
permission to test is illegal.

---

## 🔥 Hellhound.exe — Ransomware Kill-Chain Simulator

A blood-red PyQt5 visual simulation of a ransomware kill chain — **infiltration →
recon → encryption → deletion → ransom note** — played out against 256 virtual
files (~1 GB) across fake system directories in an in-memory filesystem.
**It never touches real files.** Nothing on the host is read, encrypted, or
deleted. This is an educational stage, not a weapon.

**What it does:**
- Walks the full kill chain live: infiltration, recon, encryption, deletion,
  ransom note.
- **Live terminal log, phase tracker, defense tips, and kill stats** as the attack
  unfolds.
- **1–30x speed control** — slow it down to study each phase, or let it rip.
- **No escape:** no pause button, Reset/Launch die mid-attack, and the window
  refuses to close until total destruction. It finishes what it started.
- Ends with a fake 72-hour ransom countdown and Hellhound's sign-off.

Note: the repo also hosts `HellHound.py`, the original terminal-based tool (v2.0),
which performs **real** file deletion/encryption — controlled environments only,
explicit permission required. The `.exe` is simulation-only.

**Get it:** Windows build from
[releases](https://github.com/TheRealJesusTheHacker/Hellhound.exe/releases) — the
release pipeline generates a signed build-provenance attestation with every build.

**Who it's for:** educators, students, and security-awareness training — anyone who
wants to watch a ransomware kill chain unfold with zero risk.

---

## 🐶 JadeOS — Pentesting Linux Distro

[![release](https://img.shields.io/github/v/tag/TheRealJesusTheHacker/DogOS)](https://github.com/TheRealJesusTheHacker/DogOS/releases)

🚧 **In development** — [v0.1.0 "Doberman" prerelease](https://github.com/TheRealJesusTheHacker/DogOS/releases/tag/v0.1.0) is out now (complete project
source: live-build tree, helper packages, design spec, security review, OSINT
inventory). No bootable ISO yet — the full build needs real hardware.

**"All Dogs Go To Heaven."** JadeOS is a security and penetration-testing Linux
distribution built from scratch on Debian testing, with a Kali-style rolling
toolset. MATE on X11 for maximum tool compatibility, a graphical Calamares
installer with JadeOS branding, and two flavors: kitchen-sink `full` and live-USB
friendly `lite`. Release codenames are dog breeds, starting with Doberman.

**What it ships:**
- **Pentest toolkit** — Kali metapackages (top10 on lite, everything on full), plus
  JadeOS layers: OSINT, anonymity, AI, dark-web.
- **Anonymity** — Tor, I2P, `dogos-ghost` (transparent/per-app routing, killswitch,
  captive-portal hatch), `dogos-leaktest` verification.
- **Amnesiac live mode** — Tails-style: RAM-only `toram` boot option, always-on MAC
  randomization, randomized hostname on live boot.
- **Hardened defaults** — AppArmor, Bubblewrap, nftables default-deny incoming, no
  listening services, password-required sudo, LUKS via the installer.
- **Local AI** — Ollama/llama.cpp by default; cloud APIs strictly opt-in.
- **OSINT toolkit** — installable tools, 30-service browser bookmark pack, wordlists,
  GHDB dork starters, SecLists fetcher.

**Who it's for:** pentesters, security researchers, and OSINT practitioners who want
a Kali-style daily driver built around anonymity and local AI — and anyone who'd
rather run an OS that was hardened on purpose instead of hoping the defaults are
enough.

---

## Supply chain

NitroCore, VectorZip and ShibaCuddles releases ship with SHA256 checksums —
verify before you run anything. Their release pipelines also generate signed
build-provenance attestations with every build.

The released tools run CodeQL scanning, Dependabot updates, and SHA-pinned CI —
the supply chain gets the same treatment as the code.

## Donations

If these tools earned their keep, BTC is welcome:

```
bc1qvydns2fmyjzj55wzxq7ta28nxdhcmu9l9m6yg0
```

## Contact

Business inquiries: **Sentinelsafeguard@outlook.com**
