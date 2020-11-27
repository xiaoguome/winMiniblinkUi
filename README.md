# winMiniblinkUi
基于miniblink的Windows桌面软件UI框架，小巧灵活，适用于C++语言，采用VS2019编译(Win32 x86)。

# 特性
（1）集成世界上最小的miniblink框架，方便基于HTML, Javascript，CSS等web前端技术开发桌面软件。
（2）集成常用文件操作，如选择文件、选择目录和保存文件等。
（3）集成Sqlite3数据库接口，支持加密数据库，通过js操作数据库，如常见的增、删、改、查。
（4）集成jsoncpp，且修正中文乱码问题，js和cpp可互传json格式数据。
（5）开箱即用，对于只使用数据库存储的软件可以不需修改任何源码，直接编写html页面。
（6）资源打包，提供打包工具可对html、js、css等资源打包发布。
（7）方便调试，集成开发者工具，快速调试js代码。

# 使用
（1）软件目录下建立source文件夹，用于存储所有web资源：html，js，css和图片等。
（2）source目录下创建app-loader.html，用于初始化，如创建数据库表，加入初始数据等，最后引导到软件主界面。当然，你也可以在源码中做这些工作。
（3）调试无误后，使用webpkg.exe将source文件夹打包，将创建source.dll文件。
（4）资源加载顺序：先从source.dll中查找，如果没有则从source文件夹中查找，因此调试阶段可先别生成source.dll文件，直接在source文件夹中调试。

# 发布
（1）编译生成软件主程序
（2）打包source文件夹，将source.dll和主程序放在一起
（3）将必须的dll主程序放在一起，有：node.dll，libeay32.dll。
因此文件结构为：

  |- 主程序.exe
  
  |- source.dll
  
  |- node.dll
  
  |- libeay32.dll

# 升级miniblink
请下装最新的版本，覆盖头文件wke.h和node.dll即可。
下装地址: https://github.com/weolar/miniblink49/releases
