# Commands and Permissions

## Command List

### Basic Commands

| Command | Description | Permission |
|---------|-------------|------------|
| `/gmenu` | Open the default menu | `geysermenu.use` |
| `/gmenu help` | Display help information | `geysermenu.use` |
| `/gmenu reload` | Reload configuration files | `geysermenu.reload` |
| `/gmenu open <player> <menu>` | Open a specified menu for a target player | `geysermenu.open` |

### Command Parameters

Explanation of parameters for the `/gmenu open` command:
- `<player>`: Target player name
- `<menu>`: Menu filename to open (e.g., `menu.yml`)

## Permission Nodes

### Basic Permissions

| Permission Node | Description | Default Value |
|-----------------|-------------|---------------|
| `geysermenu.use` | Allows using menu commands | true |
| `geysermenu.reload` | Allows reloading plugin configuration | op |
| `geysermenu.open` | Allows opening menus for other players | op |
| `geysermenu.*` | Allows using all features | op |

### Menu Permissions

Menu permissions are configured in `config.yml`:

```yaml
menus:
  main:
    file: "menu.yml"
    enable: true
    permission: "geysermenu.menu.main"
  
  shop:
    file: "shop.yml"
    enable: true
    permission: "geysermenu.menu.shop"
```
All menu permissions automatically become sub-permissions of `geysermenu.menu.*`.Players with the `geysermenu.menu.*`permission can use all enabled menus.