# Icon System

GeyserMenu supports two types of icons: Java Edition item IDs and Bedrock Edition texture paths.

## Basic Usage

### 1. Java Edition Item ID

Use Java Edition item IDs, and the plugin will automatically convert them to corresponding Bedrock Edition texture paths:

```yaml
items:
  - text: "Teleport Menu"
    icon: "compass"
    icon_type: "java"      # Use Java Edition item ID
```
### 2. Bedrock Edition Texture Path
Directly use Bedrock Edition texture paths:
```yaml
items:
  - text: "Shop Menu"
    icon: "textures/items/diamond"
    icon_type: "bedrock"   # Use Bedrock Edition texture path
```
## Using Resource Pack Icons
You can add custom icons through a Bedrock Edition resource pack:

1. Create the resource pack directory structure:
```plaintext
my_resource_pack/
├── manifest.json
├── pack_icon.png
└── textures/
    └── gui/
        └── icons/
            ├── my_icon1.png
            └── my_icon2.png
```
2. Use custom icons in menus:
```yaml
items:
  - text: "Custom Button"
    icon: "textures/gui/icons/my_icon1"
    icon_type: "bedrock"
```
3. Apply the resource pack to the Bedrock Edition client:
- Import the resource pack into the Bedrock Edition client
- Or distribute the resource pack automatically via the server

## Icon Mapping
Configure Java Edition to Bedrock Edition texture mapping in `config.yml`:
```yaml
icons:
  # Default icon
  default: "textures/items/paper"
  
  # Icon type mappings
  mappings:
    grass_block: "textures/blocks/grass_side"
    diamond: "textures/items/diamond"
    compass: "textures/items/compass_item"
```

## Best Practices
1. When using resource packs:

- Recommended image size: 32x32 or 64x64 pixels
- Use PNG format with transparency support
- Use lowercase letters and underscores for filenames
- Use the textures/gui/icons/ prefix for paths

2. Choosing icon types:
- If using Java Edition items, choose icon_type: "java"
- If using custom icons, choose icon_type: "bedrock"

3. Resource pack considerations:
- Ensure the resource pack version is compatible with the client
- Icon paths must be complete and correct
- It is recommended to use server-side resource pack distribution

:::tip Tip

- Custom icons must be loaded through a Bedrock Edition resource pack
- Resource packs can be loaded on the server or client side
- Icon paths are case-sensitive
:::

:::warning Note
- If an icon path is invalid, the default icon will be used
Resource packs must meet Bedrock Edition format requirements
- It is recommended to test all icons for proper display 
:::