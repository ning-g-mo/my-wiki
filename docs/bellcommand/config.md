---
sidebar_position: 3
title: 配置文件
---

## 配置文件
:::warning 注意
如果你更新了插件，请先对物品属性做好笔记或备份，删除配置文件使其重新生成！
:::
```yaml
# BellCommand 配置文件 (BellCommand Configuration File)
# 版本: 1.2.3 (Version: 1.2.3)
# 作者: 柠枺 (Author: Ningmo)

# 配置文件说明 (Configuration File Instructions):
# 1. 所有带有 '#' 的行都是注释，不会影响插件运行 (All lines starting with '#' are comments and will not affect the plugin's operation)
# 2. 颜色代码使用 '&' 符号，例如 &a 代表绿色 (Color codes use the '&' symbol, e.g., &a for green)
# 3. 在命令中可以使用 %player% 代表玩家名称 (In commands, you can use %player% to represent the player's name)
# 4. 确保修改配置后使用 /bellcommand reload 重载插件 (Make sure to use /bellcommand reload after modifying the configuration to reload the plugin)

# 重要提示 (Important Notes):
# - 请勿手动修改 config-version，这可能导致插件无法正常工作 (Do not manually modify config-version as it may cause the plugin to fail)
# - 如果插件提示配置文件版本不匹配，请删除配置文件并重启服务器 (If the plugin indicates a version mismatch, delete the configuration file and restart the server)
# - 每个版本的配置文件结构可能不同，更新插件后请参考新版本的配置说明 (Each version of the configuration file structure may differ; refer to the new version's instructions after updating the plugin)

# 配置文件版本，请勿修改 (Configuration file version, do not modify)
# 当前支持的配置文件版本: 2 (Current supported configuration file version: 2)
config-version: 2

# 调试模式 (Debug Mode)
# 启用后会输出更多的调试信息，帮助排查问题 (Enabling this outputs more debug information to help troubleshoot issues)
debug: false

# 语言设置 (Language Setting)
# 目前仅支持默认语言文件 messages.yml
language: messages

# 更新检查设置 (Update Check Settings)
update-source:
  # 是否启用自动更新检查 (Whether to enable automatic update checks)
  enabled: true
  # 更新源类型: github, gitee, custom (Update source type: github, gitee, custom)
  source: github
  # 检查更新间隔（秒）(Check interval in seconds)
  check-interval: 86400
  # 发现新版本时的提醒间隔（秒）(Reminder interval in seconds when a new version is found)
  reminder-interval: 14400
  # GitHub 更新源配置 (GitHub Update Source Configuration)
  github:
    owner: ning-g-mo
    repo: BellCommand
  # Gitee 更新源配置 (Gitee Update Source Configuration)
  gitee:
    owner: your-username
    repo: your-repo
  # 自定义更新源配置 (Custom Update Source Configuration)
  custom:
    # 自定义更新检查URL (Custom update check URL)
    # 服务器需要返回JSON格式，包含以下字段： (The server should return JSON format with the following fields:)
    # {
    #   "version": "1.0.0",        # 最新版本号（必需）(Latest version number (required))
    #   "download": "下载链接",     # 下载链接（可选）(Download link (optional))
    #   "description": "更新说明"   # 更新说明（可选）(Update description (optional))
    # }
    check-url: "https://your-api.com/bellcommand/version"
    # 是否验证 SSL 证书（如果使用自签名证书，可以设置为 false） (Whether to verify SSL certificates (set to false if using self-signed certificates))
    verify-ssl: true
    # 自定义请求头（可选） (Custom request headers (optional))
    headers:
      Authorization: "your-token"
      User-Agent: "BellCommand-UpdateChecker"

# 命令物品配置 (Command Item Configuration)
# 每个物品的配置格式如下: (Each item's configuration format is as follows:)
# items:
#   物品ID: (Item ID:)
#     item-id: 物品类型 (Minecraft 物品ID) (Item type (Minecraft item ID))
#     name: 物品显示名称 (支持颜色代码) (Item display name (supports color codes))
#     lore: 物品说明 (支持颜色代码) (Item description (supports color codes))
#     permission: 使用权限 (Usage permission)
#     cooldown: 冷却时间 (秒) (Cooldown time (seconds))
#     commands: (Commands:)
#       left-click: # 普通左键命令（Java版） (Normal left-click command (Java Edition))
#         序号: (Sequence number:)
#           command: 要执行的命令 (Command to execute)
#           as-console: 是否以控制台身份执行 (Execute as console)
#       right-click: # 普通右键命令（Java版） (Normal right-click command (Java Edition))
#         序号: (Sequence number:)
#           command: 要执行的命令 (Command to execute)
#           as-console: 是否以控制台身份执行 (Execute as console)
#       shift-left-click: # 蹲下时左键命令（Java版） (Left-click command while crouching (Java Edition))
#         序号: (Sequence number:)
#           command: 要执行的命令 (Command to execute)
#           as-console: 是否以控制台身份执行 (Execute as console)
#       shift-right-click: # 蹲下时右键命令（Java版） (Right-click command while crouching (Java Edition))
#         序号: (Sequence number:)
#           command: 要执行的命令 (Command to execute)
#           as-console: 是否以控制台身份执行 (Execute as console)
#       bedrock-left-click: # 基岩版左键命令 (Bedrock Edition left-click command)
#         序号: (Sequence number:)
#           command: 要执行的命令 (Command to execute)
#           as-console: 是否以控制台身份执行 (Execute as console)
#       bedrock-right-click: # 基岩版右键命令 (Bedrock Edition right-click command)
#         序号: (Sequence number:)
#           command: 要执行的命令 (Command to execute)
#           as-console: 是否以控制台身份执行 (Execute as console)
#       bedrock-shift-left-click: # 基岩版蹲下时左键命令 (Bedrock Edition left-click command while crouching)
#         序号: (Sequence number:)
#           command: 要执行的命令 (Command to execute)
#           as-console: 是否以控制台身份执行 (Execute as console)
#       bedrock-shift-right-click: # 基岩版蹲下时右键命令 (Bedrock Edition right-click command while crouching)
#         序号: (Sequence number:)
#           command: 要执行的命令 (Command to execute)
#           as-console: 是否以控制台身份执行 (Execute as console)
items:
  # 示例物品 - 菜单 (Example Item - Menu)
  home:
    item-id: CLOCK
    name: "&6菜单 (&6Menu)"
    lore:
      - "&7左键点击: &f打开菜单"
      - "&7右键点击: &f打开菜单"
      - "&7蹲下左键: &f打开高级菜单"
      - "&7蹲下右键: &f打开设置菜单"
      - "&7基岩版左键: &f打开基岩版菜单"
      - "&7基岩版右键: &f打开基岩版设置"
      - "&7基岩版蹲下左键: &f打开基岩版高级菜单"
      - "&7基岩版蹲下右键: &f打开基岩版高级设置"
      - "&e冷却时间: &f1.5秒"
    permission: "bellcommand.item.home"
    cooldown: 1.5  # 冷却时间(秒)，支持小数点，基于玩家游戏时间计算
    commands:
      left-click:
        1:
          command: "cd"
          as-console: false
      right-click:
        1:
          command: "cd"
          as-console: false
      shift-left-click:
        1:
          command: "cd advanced"
          as-console: false
      shift-right-click:
        1:
          command: "cd settings"
          as-console: false
      bedrock-left-click:
        1:
          command: "cd bedrock"
          as-console: false
      bedrock-right-click:
        1:
          command: "cd bedrock settings"
          as-console: false
      bedrock-shift-left-click:
        1:
          command: "cd bedrock advanced"
          as-console: false
      bedrock-shift-right-click:
        1:
          command: "cd bedrock advanced settings"
          as-console: false

# 配置文件使用提示 (Configuration File Usage Tips):
# 1. 物品ID必须是唯一的，不能重复 (Item IDs must be unique and cannot be repeated)
# 2. item-id 必须是有效的 Minecraft 物品ID (item-id must be a valid Minecraft item ID)
# 3. 权限节点建议使用插件名称作为前缀 (Permission nodes are recommended to use the plugin name as a prefix)
# 4. 冷却时间设置为 0 表示无冷却 (Setting cooldown to 0 means no cooldown)
# 5. 命令中的 %player% 会被替换为玩家名称 (The %player% in commands will be replaced by the player's name)
# 6. as-console: true 表示以控制台身份执行命令 (as-console: true means execute as console)
# 7. 可以为同一个动作（左键/右键）配置多个命令 (Multiple commands can be configured for the same action (left-click/right-click))
# 8. 确保所有命令都是服务器支持的 (Ensure all commands are supported by the server)

auto-give:
  enabled: true  是否启用自动给予
  join: true   重新加入是否给予
  first-join: true  # 是否仅在首次加入时给予
  respawn: true   #重生是否给予
  items:
    - "home"
  first-join-items:  # 首次加入时额外给予的物品
    - "tutorial_book"
    - "welcome_kit"
  save-history: true  # 是否保存玩家获取记录
  history-file: "player-history.yml"  # 玩家记录文件名

auto-cleanup:
  enabled: true  # 是否自动清理掉落的命令物品 (Whether to automatically clean up dropped command items)
  delay: 30  # 掉落物保留时间(秒) (Drop retention time in seconds)
```