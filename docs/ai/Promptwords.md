---
sidebar_position: 2
title: 初始提示词
---
在这里提供怎么写一个初始提示词。

## 格式
没有明确规定，让ai了解你的想法。
## 示例
```txt
中文名世界别名变量
英文名world alias variables
简称&命令scv
包名cn.ningmo
API: bukkit 1.21
简介:为你的世界设置任何别名且以占位符的形式应用在其他地方。
功能:调用世界名称生成名字为%wav%的世界别名占位符并应用在其他地方。
。世界别名支持任何字符串，支持颜色代码。
配置文件
#-------------------
#     +wav配置文件+
#     作者:柠枺
#-------------------
#提示
#变量占位符为%wav_<world>%
#是否开启调试日志
debug: false
#已应用的世界
world:
 - world
 - world_end
 - 等等……

#世界别名
world_alias_variables:
 world: "&a主世界"
 world_end: "&s末地 "
 等等……
 
```

:::::info 提示
提示词可以不包含配置文件内容，让ai了解你的想法。  
空白项目(指项目目录中没有文件)需要提供包名和项目名称。
::::warning 注意
如果你已经通过IDEA的minecraft插件形成了空白项目，请一定要告诉ai你的项目名和包名！
:::info 提示
如果你在聊天上下文中提供了主类，那么包名和项目名称不是必须的。  
:::::

## 实战示例(cursor的Claude3.5作为展示)
先创建一个空白项目，通过cursor打开，然后ctrl+i 打开cursor的ai对话框换成claude3.5，模式改成edit模式(编辑模式)，输入以下内容：
![输入提示词](/img/promptwords/promptwords.png)
回车确认，等ai完成任务。  
![任务完成](/img/promptwords/image.png)  
点击accept all 按钮接受ai的所有更改，至此，你的项目已经初始化完毕。

:::danger 注意
不要一次性给ai提供过度的功能任务，或者很难实现的功能任务，否则ai写出来的就不是你是的想法了。
:::
