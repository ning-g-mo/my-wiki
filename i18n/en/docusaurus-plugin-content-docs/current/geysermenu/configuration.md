# Configuration Details

## Main Configuration File

The `config.yml` file contains the core settings for the plugin:

### Performance Settings

```yaml
performance:
  # Command execution delay (milliseconds)
  command-delay: 0
  
  # PlaceholderAPI variable caching
  cache-placeholders: false
  cache-refresh: 30
  max-cache-size: 1000
```

### Security Settings

```yaml
security:
  # Blocked commands
  blocked-commands:
    - "op"
    - "deop"

  # Special character check
  allow-special-chars: false
  
  # File path security check
  check-file-path: true
```
### Icon Settings

GeyserMenu supports two types of icons:

### 1. Java Edition Item ID
Use Java Edition item IDs, which will be automatically converted to corresponding Bedrock Edition texture paths:

```yaml
items:
  - text: "Teleport Menu"
    icon: "compass"      # Java Edition item ID
    icon_type: "java"    # Specify using Java Edition icons
```

### 2. Bedrock Edition Texture Path
Directly use Bedrock Edition texture paths:

```yaml
items:
  - text: "Shop Menu"
    icon: "textures/items/diamond"    # Bedrock Edition texture path
    icon_type: "bedrock"             # Specify using Bedrock Edition icons
```

### Icon Mapping Configuration

Configure Java Edition to Bedrock Edition texture mapping in `config.yml`:

```yaml
icons:
  # Default icon
  default: "textures/items/paper"
  
  # Icon type mappings (Java Edition -> Bedrock Edition)
  mappings:
    # Blocks
    grass_block: "textures/blocks/grass_side"
    stone: "textures/blocks/stone"
    dirt: "textures/blocks/dirt"
    
    # Items
    diamond: "textures/items/diamond"
    compass: "textures/items/compass_item"
    book: "textures/items/book_normal"
```

### Usage Recommendations

1. If you are familiar with Java Edition item IDs, use `icon_type: "java"`
2. If you need specific Bedrock Edition textures, use `icon_type: "bedrock"`
3. If `icon_type`is not specified, it defaults to attempting to process as a Java Edition item ID

:::tip tip
- Java Edition item IDs do not require the `minecraft:` prefix
- Bedrock Edition texture paths must be complete texture paths
- You can add new texture mappings in the configuration file
- Icon types must be specified via `icon_type` ("java" or "bedrock")
:::

:::warning Note
If Java edition item ID does not have a mapping, the default icon will be used.
:::

## Message Configuration

The `messages.yml`  file is used to configure all text messages for the plugin:

```yaml
prefix: "§6[GeyserMenu] §f"  # Message prefix

reload:
  success: "§aConfiguration reloaded successfully!"  # Reload success message
  start: "§eReloading plugin configuration..."  # Start reload message

error:
  no-permission: "§cYou do not have permission to execute this command!"  # Permission denied message
  # ... other error messages
```

## Menu Configuration

Explanation of menu file structure:

### Basic Structure

```yaml
menu:
  # Menu title
  title: "Main Menu"
  
  # Subtitle (optional)
  subtitle: "Choose an option"
  
  # Main content (optional)
  content: "This is the menu content"
  
  # Footer (optional)
  footer: "Online players: %server_online%"
  
  # Button list
  items:
    - text: "Teleport Menu"
      description: "Open the teleport menu"
      icon: "compass"
      icon_type: "java"      # Must specify icon type
      submenu: "teleport.yml"
    
    - text: "Shop Menu"
      description: "Open the shop menu"
      icon: "textures/items/diamond"
      icon_type: "bedrock"   # Must specify icon type
      submenu: "shop.yml"
    
    - text: "Return to Spawn"
      description: "Click to teleport to spawn"
      icon: "nether_star"
      icon_type: "java"    # Add icon type
      command: "spawn"
```

:::tip Tip
- All text supports color codes (use & symbol)
- Supports PlaceholderAPI variables
- Icon types must be specified via `icon_type` ("java" or "bedrock") 
:::

## Configuration Saving

Mechanism for saving and reloading configuration files:

1. All default configuration files are generated on first startup
2. Subsequent modifications to configuration files will not be overwritten
3. Use  `/gmenu reload` to reload configurations while retaining changes

:::warning warning
 Note Do not delete configuration files while the server is running, as this may cause the plugin to malfunction.
::: 

## Directory Explanation

### Menus Directory

The `menus` directory is used to store menu configuration files:
- Uses YAML format
- Filename serves as the menu name
- Supports organizing menus into subdirectories