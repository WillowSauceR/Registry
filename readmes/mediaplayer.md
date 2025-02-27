# 简介
本插件用于在BDS服务器播放NBS音乐和地图视频。

## 使用
### NBS 音乐播放
NBS音乐文件请放置到``plugins\MediaPlayer\nbs``文件夹中

在游戏中使用``/mpm``作为主命令
子命令为``list``，``play``和``stop``。

| 子命令 | 参数     | 示例        | 解释              |
| ------ | -------- | ----------- | ----------------- |
| list   | 无       | /mpm list   | 获取歌曲索引      |
| play   | 歌曲索引 | /mpm play 1 | 播放歌曲(索引为1) |
| stop   | 无       | /mpm stop   | 停止播放          |

注意：在播放音乐之前，请先使用``/mpm list``来获取音乐列表。
具体使用方法，也可以在游戏内使用``/mpm``命令查看
如果``plugins\MediaPlayer\video``文件夹下存在与音乐同名的视频，那么将会一同播放（如果玩家手持已使用的地图）
比如存在如下文件和文件夹，那么插件将会尝试同时播放音乐和视频：
``plugins\MediaPlayer\nbs\test.nbs``
``plugins\MediaPlayer\video\test``

#### 推荐NBS音乐资源
制作原创nbs音乐可不容易呢~来支持一下他们吧

[原创nbs音乐集合](https://www.minebbs.com/resources/nbs.4773/)

[nbs音乐《water》](https://www.minebbs.com/resources/nbs-water.4365/)

[nbs音乐集合](https://github.com/nickg2/NBSsongs)

### 视频播放
视频文件夹请放置到``plugins\MediaPlayer\video``文件夹中

在游戏中使用``/mpv``作为主命令
子命令为``list``，``play``和``stop``。

| 子命令 | 参数     | 示例        | 解释              |
| ------ | -------- | ----------- | ----------------- |
| list   | 无       | /mpv list   | 获取视频索引      |
| play   | 视频索引 | /mpv play 1 | 播放视频(索引为1) |
| stop   | 无       | /mpv stop   | 停止播放          |

注意：在播放视频之前，请先使用``/mpv list``来获取视频列表。且必须手持已使用的地图
具体使用方法，也可以在游戏内使用``/mpv``命令查看

#### 生成可播放的视频文件
概述：
我们使用``ffmpeg``将视频转换为128x128分辨率，20FPS。
然后将视频中的每一帧提取为单个图片，再由插件进行播放。

首先，在[此处](https://www.gyan.dev/ffmpeg/builds/ffmpeg-git-full.7z)下载``ffmpeg``
将其解压，并将``bin``文件夹中的``ffmpeg.exe``放入服务端下的``plugins\MediaPlayer\video``文件夹
将你需要生成的视频重命名为``input.mp4``，并且放入服务端下的``plugins\MediaPlayer\video``文件夹
在``plugins\MediaPlayer\video``文件夹中打开``convert.bat``进行转换。

如果转换成功，应该会产生一个名为``output``的文件夹，如果有与之匹配的音乐，你可以将其重命名为和音乐同名。插件会在播放音乐的同时自动播放视频。
请将``input.mp4``和``output.mp4``两个文件删除，以便于下一次转换。

## 致谢

- [yqs112358](https://github.com/yqs112358) 提供了在发包层面的技术支持
- [lgc2333](https://github.com/lgc2333) 参与了[nbsparser](https://github.com/WillowSauceR/nbsparser)的开发，提供了基础技术支持

没有他们的支持，这个项目不可能实现
