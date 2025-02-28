---
sidebar_position: 2
title: Getting Started
---

1. Ensure your server has the required prerequisites installed:
   - Geyser-Spigot
   - Floodgate

2. Download GeyserMenu v1.1.8

3. Place the plugin in the server's `plugins` folder

4. Restart the server

## Directory Structure

On the first run, the plugin will generate the following directories and files:

```text
plugins/GeyserMenu/
├── config.yml      # Main configuration file
├── messages.yml    # Message configuration file
└── menus/          # Menu folder
    ├── menu.yml    # Main menu
    ├── shop.yml    # Shop menu
    └── teleport.yml # Teleport menu
```
:::tip Tip

- Configuration files are only generated on the first startup; subsequent modifications will not be overwritten.
- Place menu files in the `menus` directory. 
:::
## Configuration
### Basic Configuration
Edit `config.yml` for basic settings:
```yaml
settings:
  default-menu: "menu.yml"  # Default menu
  debug: false              # Debug mode
```
### Creating Menus
Create new YAML files in the `menus` folder:
```yaml
menu:
  title: "My Menu"
  subtitle: "Choose an option"
  content: "This is the menu content"
  items:
    - text: "Teleport Menu"
      description: "Open the teleport menu"
      icon: "compass"
      icon_type: "java"     # Use Java Edition item ID
      submenu: "teleport.yml"
    
    - text: "Execute Command"
      description: "Click to execute a command"
      icon: "textures/items/diamond"
      icon_type: "bedrock"  # Use Bedrock Edition texture path
      command: "say Hello"
```
:::tip Tip
- Each button must have `text` and `icon`
- Choose either `command` or `submenu`
- `description` is optional
- Icons must specify their type (`java` or `bedrock`)
:::

## Usage
1. Bedrock Edition players can open the default menu by typing /gmenu

2. Use /gmenu help to view all available commands

3. Administrators can use /gmenu reload to reload the configuration