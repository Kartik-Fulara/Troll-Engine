# \# TrollEngine

# 

# Advanced Minecraft trolling and event automation engine for Paper/Spigot servers.

# 

# TrollEngine provides:

# 

# \* real-time troll command execution

# \* embedded HTTP → RCON bridge

# \* advanced death tracking

# \* viewer attribution

# \* troll mob/effect tracking

# \* cascade kill systems

# \* live command execution

# \* fully embedded Java infrastructure

# 

# No Python.

# No Docker.

# No external bridge process.

# 

# Everything runs directly inside the plugin.

# 

# \---

# 

# \# Features

# 

# \## Embedded HTTP Bridge

# 

# TrollEngine includes a fully embedded Java HTTP bridge.

# 

# The plugin exposes its own API directly from inside the Minecraft server and forwards commands internally through RCON.

# 

# Supported endpoints:

# 

# ```http

# POST /

# POST /rcon

# POST /cmd

# GET  /health

# ```

# 

# Features:

# 

# \* multi-threaded HTTP server

# \* request authentication

# \* automatic heartbeat monitoring

# \* graceful restart support

# \* zero external dependencies

# \* no Docker or Python required

# 

# \---

# 

# \# Advanced Death Tracking

# 

# Tracks and classifies every player death.

# 

# Supported death types:

# 

# \* natural deaths

# \* command deaths

# \* plugin-forced deaths

# \* troll mob kills

# \* troll effect kills

# \* void deaths

# \* cascade deaths

# 

# Every death event includes:

# 

# \* player

# \* cause

# \* executor

# \* timestamp

# \* attribution source

# \* death type

# 

# \---

# 

# \# Viewer Attribution System

# 

# TrollEngine automatically attributes troll actions to the correct user/viewer.

# 

# Supported attribution systems:

# 

# \* `/kill`

# \* spawned mobs

# \* potion effects

# \* forced deaths

# \* chained events

# \* cascade kills

# 

# Example:

# 

# ```txt

# viewer123 spawned a zombie

# viewer123 applied poison

# viewer123 triggered a cascade

# ```

# 

# \---

# 

# \# Troll Mob Tracking

# 

# Every mob spawned during an active troll event is tagged automatically.

# 

# Supported:

# 

# \* zombies

# \* skeletons

# \* creepers

# \* custom entities

# \* summoned mobs

# \* projectile attribution

# 

# If a tagged mob kills a player:

# 

# \* the kill is attributed correctly

# \* custom death messages are generated

# \* statistics are updated automatically

# 

# \---

# 

# \# Troll Effect Tracking

# 

# Tracks lethal effects applied during troll events.

# 

# Supported effects:

# 

# \* poison

# \* wither

# \* instant damage

# \* void-related deaths

# 

# The plugin preserves attribution even when deaths occur later.

# 

# \---

# 

# \# Cascade Death System

# 

# When a tracked death occurs:

# 

# \* global broadcasts can trigger

# \* titles/subtitles can display

# \* chain reactions can execute

# \* other players can be affected automatically

# 

# Includes:

# 

# \* cascade protection

# \* duplicate prevention

# \* configurable delay system

# \* root death tracking

# 

# \---

# 

# \# Internal Command System

# 

# Built-in commands for:

# 

# \* troll execution

# \* bridge management

# \* stats

# \* viewer attribution

# \* runtime reloads

# 

# Commands:

# 

# ```txt

# /trollspawn

# /trollsetuser

# /trollstats

# /trollreloadbridge

# /trollfetchmsgs

# ```

# 

# \---

# 

# \# Embedded RCON Client

# 

# Includes a fully embedded thread-safe RCON client implementation.

# 

# Features:

# 

# \* atomic command batches

# \* automatic authentication

# \* connection isolation

# \* request locking

# \* timeout handling

# \* concurrent request safety

# 

# No external RCON libraries required.

# 

# \---

# 

# \# Performance

# 

# Designed for production environments.

# 

# Features:

# 

# \* concurrent-safe systems

# \* async persistence

# \* lightweight HTTP server

# \* lock-safe RCON execution

# \* low memory overhead

# \* automatic cleanup systems

# 

# \---

# 

# \# Architecture

# 

# TrollEngine is built entirely in Java.

# 

# Core systems:

# 

# \* embedded HTTP server

# \* RCON bridge

# \* death tracking engine

# \* effect attribution system

# \* entity tracking system

# \* command attribution tracker

# \* statistics manager

# 

# No external runtime required.

# 

# \---

# 

# \# Installation

# 

# \## Requirements

# 

# \* Java 21+

# \* Paper / Spigot / Purpur

# \* Minecraft 1.20+

# \* RCON enabled

# 

# \---

# 

# \# Setup

# 

# \## 1. Install Plugin

# 

# Place:

# 

# ```txt

# TrollEngine.jar

# ```

# 

# inside:

# 

# ```txt

# /plugins/

# ```

# 

# \---

# 

# \## 2. Enable RCON

# 

# Inside `server.properties`:

# 

# ```properties

# enable-rcon=true

# rcon.port=25575

# rcon.password=CHANGE\_ME

# ```

# 

# \---

# 

# \## 3. Configure Bridge

# 

# Edit:

# 

# ```txt

# plugins/TrollEngine/config.yml

# ```

# 

# Example:

# 

# ```yaml

# bridge:

# &#x20; enabled: true

# 

# &#x20; bind-host: ""

# &#x20; port: 8880

# 

# &#x20; secret-token: "CHANGE\_ME"

# 

# &#x20; rcon-host: "127.0.0.1"

# &#x20; rcon-port: 25575

# &#x20; rcon-password: "CHANGE\_ME"

# 

# &#x20; rcon-timeout-ms: 5000

# ```

# 

# \---

# 

# \# API Usage

# 

# Execute commands:

# 

# ```bash

# curl -X POST http://SERVER\_IP:8880/rcon \\

# &#x20; -H "Content-Type: application/json" \\

# &#x20; -H "X-Token: YOUR\_SECRET" \\

# &#x20; -d '{

# &#x20;   "commands": \[

# &#x20;     "say hello world"

# &#x20;   ]

# &#x20; }'

# ```

# 

# Health check:

# 

# ```bash

# curl http://SERVER\_IP:8880/health

# ```

# 

# \---

# 

# \# Statistics

# 

# Built-in death statistics system.

# 

# Tracks:

# 

# \* global deaths

# \* per-player deaths

# \* troll kills

# \* natural deaths

# \* command kills

# \* cascade events

# 

# Use:

# 

# ```txt

# /trollstats

# ```

# 

# \---

# 

# \# Security

# 

# Recommended production setup:

# 

# \* firewall protected bridge

# \* reverse proxy

# \* secure token configuration

# \* localhost RCON binding

# \* restricted port access

# 

# Never expose raw RCON publicly.

# 

# \---

# 

# \# Compatibility

# 

# Supported servers:

# 

# \* Paper

# \* Spigot

# \* Purpur

# 

# Supported versions:

# 

# \* 1.20.x

# \* 1.21.x

# 

# \---

# 

# \# Releases

# 

# This repository contains:

# 

# \* compiled binaries

# \* release assets

# \* changelogs

# \* update manifests

# 

# The full source code is private.

# 

# \---

# 

# \# Download

# 

# Latest release:

# 

# ```txt

# https://github.com/Kartik-Fulara/Troll-Engine/releases/latest

# ```

# 

# Latest API:

# 

# ```txt

# https://api.github.com/repos/Kartik-Fulara/Troll-Engine/releases/latest

# ```

# 

# \---

# 

# \# Release Assets

# 

# Each release includes:

# 

# ```txt

# TrollEngine.jar

# manifest.json

# TrollEngine.jar.sha256

# ```

# 

# \---

# 

# \# License

# 

# Binary distribution only.

# 

# Source code is private and not included in this repository.



