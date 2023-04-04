# join_message插件

服务器启动后, 每名玩家(由xuid区分不同玩家)可以自定义一段文本信息, 这段信息在接下来每次自己进入该服务器时, 都会想服内所有玩家播报.

## 用法

聊天框键入以下命令即可:
1. "-jm:set xxxx"
2. "-jm:get"
3. "-jm:erase"

"-jm:set xxxx":
- 命令用于设定自己此后进入本服务器时向其他玩家通知的内容; 
- 其中"xxxx"为自定义文本; 
- 本指令每一次重复调用都会覆盖掉上一次设定的文本.
- 例如, "-jm:set §4我上号啦!"

"-jm:get":
- 命令用于查看自己设定的自定义文本;
- 该文本将出现在聊天记录中, 仅本人可见.

"-jm:erase":
- 命令用于删除先前自己设定过的自定义文本.

## 深入了解
- 本插件在服务器启动时会读取plugins/.join_message/id_msg.json中的内容, 服务器启动后不再依赖该json文件. 
- 服务器关闭时将所有玩家的自定义信息存入该json文件中, 如果该文件此刻不存在, 那么插件将会自行创建并保存. 
- 服务器管理员甚至可以通过直接编辑该json文件来实现定义每位玩家的自定义文本内容.

## 其他

如果你需要基于本插件的某些功能进行二次开发, 那么请移步本插件的tooth存储库([点此跳转](https://github.com/LymoProjects/joinMessageBuild)), 该存储库内的代码已经做好了封装, 可以让你依赖其进行开发.