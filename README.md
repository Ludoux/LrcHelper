访问 [Release 页面](https://github.com/Ludoux/LRCHelper/releases)来获得最新的发布版本，或者手动编译代码尝鲜(但通常二进制文件与源代码所对应) 

-----

**运行要.NET Framework4.5.2@Windows的支持**

针对网易云音乐开发，根据提供的歌曲ID或歌单ID自动下载整理歌词包括翻译的功能，顺便为  SONY®WALKMAN® 设计了翻译延迟1秒的功能。

## 具体操作方法(严谨向)

(目前版本去除了手动模式，若有需要烦请 Release 页面下载 Pre-release 的v0.0.0-beta 版本)

输入对应的ID号并选择ID所对应的含义(Music or Playlist)，然后点击按钮"GET"。

1. 若为是音乐ID，lrc文件(UTF-8)会在软件所处目录下生成，结束时会弹窗通知
2. 若为是歌单ID，lrc文件(UTF-8)会在软件所处目录的以歌单名命名的文件夹中生成，页面假死，结束时不会弹窗通知。无论是否出现错误均有 log.txt 文件生成

## Tips:

1. 翻译比外文歌词慢一秒。你可以修改实现方法。
2. 软件提示文白间杂，中英具备，就是不讲语法。会意即可无需深究。
3. 操作是在主线程上所以界面假死，可以看文件数目来看进度。
4. 目前歌词歌单仅支持网易云。后期会以附加组件的方式进行弥补。
5. 编译要Json90r1的支持(引用了Newtonsoft.Json),dll是Net45版本。运行要.NET Framework4.5.2的支持

## TO DO:

1. 更改UI
2. 继续封装，完善代码安全性和可维护性
3. UI和实现线程分离

## License:

在[MIT 协议](https://mit-license.org/)下发布.

## 参考&感谢:

获取外文歌词的代码基于ituff的[163lyric项目](https://github.com/ituff/163lyric)的实现，进行了修改。(但是ituff并没有指定那个项目的开源协议)

感谢Moonlib.com的所有人Moon在这个博客上发表了[自己整理的API](http://moonlib.com/606.html)。

## 更新信息(最近在上)
* 2017.2.5 允许取消操作，有BUG，使用Task实现UI和下载线程分离，修复LICENSE编码错误，不稳定的代码版本
* 2017.2.4  使用了TPL类库实现了并行循环下载@Playlist模式，速度较原先提高了50%；优化代码，Fix Bugs(v1.0.1 Release)
* 2017.1.25 粗略的代码重构，重写了实现。未广泛测试(v1.0.0 Release)
* 2016.9.2   Fix Bugs(v0.0.0-beta Release)
* 2016.8.30 Log文件内容实现对齐，AUTO实现执行线程与UI线程分离，可实时看进度与错误数
* 2016.8.29 初版