---
sidebar_position: 3
title: 尝试构建
---
构建你的插件。

## 空白项目的构建(指没有pom.xml或build.gradle)
继续在聊天栏中输入一下请求:  
![alt text](/img/build/image.png)  
之后问题来了，ai使用了JAVA17，而项目mc版本是1.21，所以需要修改JAVA版本。
![alt text](/img/build/image1.png)  
你可以手动更改JAVA版本，也可以使用ai进行修改。

## 构建项目(有pom.xml或build.gradle)
通过IDEA打开项目，右下角会有消息提示是否加载maven/gradle项目，点击加载。  
maven为例:  
![alt text](/img/build/image2.png)  
双击运行maven/package开始进行构建。  
如果报错，直接复制错误信息，在聊天栏中输入错误日志部分，可以额外提问:  
![alt text](/img/build/image3.png)  

如果构建成功，会在项目的`target`目录下生成一个`项目名称-1.x.x.jar`文件，这个就是你的插件了。