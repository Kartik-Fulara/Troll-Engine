<div align="center">

# 🧟‍♂️ TrollEngine

**Advanced Minecraft trolling and event automation engine for Paper/Spigot servers.**

[![Java](https://img.shields.io/badge/Java-21+-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://openjdk.org/)
[![Minecraft](https://img.shields.io/badge/Minecraft-1.20%20%7C%201.21-1FCB4A?style=for-the-badge&logo=minecraft&logoColor=white)](https://minecraft.net/)
[![Paper](https://img.shields.io/badge/Paper-Supported-black?style=for-the-badge)](https://papermc.io/)
[![Spigot](https://img.shields.io/badge/Spigot-Supported-orange?style=for-the-badge)](https://www.spigotmc.org/)
[![Purpur](https://img.shields.io/badge/Purpur-Supported-blue?style=for-the-badge)](https://purpurmc.org/)
<br>
[![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)](#)
[![Releases](https://img.shields.io/badge/Releases-Download-blueviolet?style=for-the-badge)](https://github.com/Kartik-Fulara/Troll-Engine/releases)
[![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)](LICENSE)

</div>

---

## 📖 Overview

TrollEngine provides real-time troll command execution, an embedded HTTP to RCON bridge, advanced death tracking, viewer attribution, troll mob/effect tracking, cascade kill systems, and live command execution.

Everything operates on a fully embedded Java infrastructure.
* No Python.
* No Docker.
* No external bridge process.

Everything runs directly inside the plugin.

---

## ✨ Features

### 🔌 Embedded HTTP Bridge

TrollEngine includes a fully embedded Java HTTP bridge. The plugin exposes its own API directly from inside the Minecraft server and forwards commands internally through RCON.

**Supported endpoints:**
* `POST /`
* `POST /rcon`
* `POST /cmd`
* `GET /health`

**Bridge Features:**
* multi-threaded HTTP server
* request authentication
* automatic heartbeat monitoring
* graceful restart support
* zero external dependencies
* no Docker or Python required

---

### 💀 Advanced Death Tracking

Tracks and classifies every player death.

**Supported death types:**
* natural deaths
* command deaths
* plugin-forced deaths
* troll mob kills
* troll effect kills
* void deaths
* cascade deaths

**Every death event includes:**
* player
* cause
* executor
* timestamp
* attribution source
* death type

---

### 👁️ Viewer Attribution System

TrollEngine automatically attributes troll actions to the correct user/viewer.

**Supported attribution systems:**
* `/kill`
* spawned mobs
* potion effects
* forced deaths
* chained events
* cascade kills

**Example Output:**
* viewer123 spawned a zombie
* viewer123 applied poison
* viewer123 triggered a cascade

---

### 🧟 Troll Mob Tracking

Every mob spawned during an active troll event is tagged automatically.

**Supported:**
* zombies
* skeletons
* creepers
* custom entities
* summoned mobs
* projectile attribution

**If a tagged mob kills a player:**
* the kill is attributed correctly
* custom death messages are generated
* statistics are updated automatically

---

### 🧪 Troll Effect Tracking

Tracks lethal effects applied during troll events.

**Supported effects:**
* poison
* wither
* instant damage
* void-related deaths

The plugin preserves attribution even when deaths occur later.

---

### 💥 Cascade Death System

**When a tracked death occurs:**
* global broadcasts can trigger
* titles/subtitles can display
* chain reactions can execute
* other players can be affected automatically

**Includes:**
* cascade protection
* duplicate prevention
* configurable delay system
* root death tracking

---

### ⌨️ Internal Command System

Built-in commands for troll execution, bridge management, stats, viewer attribution, and runtime reloads.

**Commands:**
* `/trollspawn`
* `/trollsetuser`
* `/trollstats`
* `/trollreloadbridge`
* `/trollfetchmsgs`

---

### ⚙️ Embedded RCON Client

Includes a fully embedded thread-safe RCON client implementation. No external RCON libraries required.

**Features:**
* atomic command batches
* automatic authentication
* connection isolation
* request locking
* timeout handling
* concurrent request safety

---

### 🚀 Performance & Architecture

Designed for production environments, TrollEngine is built entirely in Java. No external runtime required.

**Performance Features:**
* concurrent-safe systems
* async persistence
* lightweight HTTP server
* lock-safe RCON execution
* low memory overhead
* automatic cleanup systems

**Core Systems:**
* embedded HTTP server
* RCON bridge
* death tracking engine
* effect attribution system
* entity tracking system
* command attribution tracker
* statistics manager

---

## 📦 Setup & Installation

### Requirements
* Java 21+
* Paper / Spigot / Purpur
* Minecraft 1.20+
* RCON enabled

### 1. Install Plugin
Place `TrollEngine.jar` inside the `/plugins/` directory.

### 2. Enable RCON
Inside `server.properties`, ensure the following are set:
* `enable-rcon=true`
* `rcon.port=25575`
* `rcon.password=CHANGE_ME`

### 3. Configure Bridge
Edit `plugins/TrollEngine/config.yml`.
Configure the bridge to be enabled, set the bind port (e.g., `8880`), set your `secret-token`, and match the RCON host, port, and password to your server properties. 

---

## 💻 API Usage

Execute commands by sending a JSON payload via POST to `http://SERVER_IP:8880/rcon`, including your `X-Token` header.
Health checks can be performed via GET request to `http://SERVER_IP:8880/health`.

---

## 📊 Statistics

The built-in statistics system tracks global deaths, per-player deaths, troll kills, natural deaths, command kills, and cascade events.
Access this via the `/trollstats` command.

---

## 🛡️ Security

Never expose raw RCON publicly. 
Recommended production setup:
* firewall protected bridge
* reverse proxy
* secure token configuration
* localhost RCON binding
* restricted port access

---

## ⬇️ Releases & Compatibility

**Supported Servers:** Paper, Spigot, Purpur.
**Supported Versions:** 1.20.x, 1.21.x.

This repository contains compiled binaries, release assets, changelogs, and update manifests. The full source code is private.

**Downloads:**
* Latest Release: `https://github.com/Kartik-Fulara/Troll-Engine/releases/latest`
* Latest API: `https://api.github.com/repos/Kartik-Fulara/Troll-Engine/releases/latest`

**Release Assets Include:**
* `TrollEngine.jar`
* `manifest.json`
* `TrollEngine.jar.sha256`

---

## 📄 License

Binary distribution only. 
Source code is private and not included in this repository.

For full terms and conditions, please refer to the included **[LICENSE](LICENSE)** file.