# Steam Deck Emulation Stack

A Steam Deck configured as an unattended retro-gaming machine — EmulationStation-DE as the front end, 17,000+ games across 36 platforms available via a network mount, and a complete offline-accessible catalog. No Steam required. No internet required at play time.

> *This repo is a public overview. The running code is private.*

---

## What it is

A Steam Deck boots into ES-DE and acts as a universal emulation front end for a multi-TB ROM library that lives on a home NAS. The Deck never stores the library itself — it mounts it over the network, so the exact same library is instantly available on multiple devices, and the Deck's SSD stays free for SteamOS and saves.

## What it does

- **Boots straight into ES-DE** — no desktop fumbling, picks up the controller immediately
- **Mounts the ROM library over the network** (FUSE mount, read-only)
- **Runs every major emulator** — RetroArch, Dolphin, PCSX2, Cemu, Eden, MAME, and more
- **Catalogs 17,000+ games across 36 platforms** with artwork and metadata
- **Auto-saves to the NAS** — save states travel with the library, not with the device
- **Includes the migration scripts** that moved 7 TB / 580,000+ files off a near-full central share onto a dedicated drive — resumable, verified, no data loss

## Software

| Layer | Tech |
|---|---|
| Device | Steam Deck (SteamOS / Bazzite) |
| Front end | EmulationStation-DE |
| Emulators | RetroArch, Dolphin, PCSX2, Cemu, Eden, MAME, others |
| Library storage | Home NAS with FUSE network mount |
| Migration | robocopy with incremental resume + verification |

## What this demonstrates

- **Physical + network architecture** — the Deck is a thin client; the library is central
- **Operational scripting at scale** — multi-TB migration without data loss, resumable checkpoints
- **Off-the-shelf composition** — no custom software, just sharp configuration of existing tools

## Stack

![Steam Deck](https://img.shields.io/badge/Steam_Deck-1A1A1A?style=flat&logo=steam&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![RetroArch](https://img.shields.io/badge/RetroArch-000000?style=flat&logo=retroarch&logoColor=white)

## Related in the AIOS Portfolio

- **[NAS Plex Tools](https://github.com/mikecutillo/nas-plex-tools)** — Python toolkit for Plex libraries on the same NAS; renaming, flattening, metadata backfill
- **[Twin Sync](https://github.com/mikecutillo/twin-sync)** — Mac/PC workflow sync via rsync + shared NAS; another Mac/PC/NAS-resident workflow

---

Part of the AIOS portfolio. See the [profile README](https://github.com/mikecutillo) for the full system map.
