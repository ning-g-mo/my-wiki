---
sidebar_position: 1
title: Home
---

# GeyserMenu v1.1.8

A lightweight and simple custom form plugin for Bedrock Edition.

## Features

- 🎮 Menu system designed specifically for Bedrock Edition players
- 📝 Fully customizable menu configuration
- 🔒 Built-in security checks
- 🚀 High performance and lightweight
- 💡 Supports PlaceholderAPI variables
- 🎨 Supports two types of icons:
  - Java Edition item IDs (automatically mapped to Bedrock Edition)
  - Bedrock Edition texture paths (used directly)

## System Requirements

- Java 21 or higher
- Spigot/Paper 1.21.1 or higher
- [Geyser-Spigot](https://geysermc.org/) and [Floodgate](https://wiki.geysermc.org/floodgate/)

## Quick Start

1. Download the latest version of GeyserMenu
2. Place the plugin in the server's plugins folder
3. Start the server, and the plugin will automatically generate configuration files
4. Edit `plugins/GeyserMenu/config.yml` for basic configuration
5. Edit or add menus in `plugins/GeyserMenu/menus/`

## Basic Commands

- `/gmenu` - Open the default menu
- `/gmenu help` - Display help information
- `/gmenu reload` - Reload the configuration file
- `/gmenu open <player> <menu>` - Open a menu for a specified player

## Permission Nodes

- `geysermenu.use` - Allows using menu commands
- `geysermenu.reload` - Allows reloading the plugin configuration
- `geysermenu.open` - Allows opening menus for other players
- `geysermenu.*` - Allows using all features