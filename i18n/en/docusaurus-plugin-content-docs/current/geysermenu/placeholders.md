# Placeholder Support

GeyserMenu supports PlaceholderAPI placeholders, which can be used to dynamically display information in menus.

## Using Placeholders

Placeholders can be used in the following locations:

- Menu title
- Menu subtitle
- Menu content
- Menu footer
- Button text
- Button description
- Commands

## Example Configuration

```yaml
menu:
  # Using a placeholder in the title
  title: "§6%player_name%'s Menu"
  
  # Using a placeholder in the content
  content: |- 
    §fHello, %player_name%
    §7Balance: §e%vault_eco_balance%
  
  # Using a placeholder in the footer
  footer: "§8Online Players: %server_online%"
  
  items:
    - text: "§eMy Balance: %vault_eco_balance%"
      description: "§7Click to view details"
      icon: "diamond"
      icon_type: "java"
      command: "balance %player_name%"
```
## Performance Optimization
To improve performance, you can configure placeholder caching in `config.yml`:
```yaml
performance:
  # Enable placeholder caching
  cache-placeholders: true
  
  # Cache refresh interval (seconds)
  cache-refresh: 30
  
  # Maximum cache size
  max-cache-size: 1000
  
  # Clear cache on reload
  clear-cache-on-reload: true
```

:::tip Tip
- Enabling caching can improve performance but may introduce delays in placeholder updates.
- Adjust the refresh interval based on your server's needs.
- For real-time updates, consider disabling caching. 
:::

## Common Placeholders
Here are some commonly used PlaceholderAPI placeholders:
- `%player_name%` - Player name
- `%player_displayname%` - Player display name
- `%server_online%` - Number of online players
- `%vault_eco_balance%` - Player balance (requires Vault)
- `%player_health%` - Player health
- `%player_food_level%` - Player hunger level

:::warning 
Note Ensure that PlaceholderAPI and the corresponding extensions are installed before using placeholders. 
:::
