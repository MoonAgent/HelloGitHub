#《HelloGitHub》第08期
>兴趣是最好的老师，[《HelloGitHub》](https://github.com/521xueweihan/HelloGitHub)就是帮你找到兴趣！

![](https://github.com/521xueweihan/HelloGitHub/blob/master/01/img/hello-github.jpg)

## 简介
最开始我只是想把自己在浏览GitHub过程中，发现的有意思、高质量、容易上手的项目收集起来，这样便于以后查找和学习。后来一想，如果给这些GitHub项目都加上简单的效果图和一些通俗易懂的中文介绍。应该能够帮助到我这样的新手激发兴趣去参与、学习这些优秀、好玩的开源项目。

所以，我就做了一个面向**编程新手**、**热爱编程**、**对开源社区感兴趣** 的人群的月刊，月刊的内容包括：**各种编程语言的项目**、**各种让生活变得更美好的工具**、**书籍、学习笔记、教程等**。这些项目都是非常容易上手，而且非常Cool，主要是希望大家能动手用起来，加入到**开源社区**中。会编程的可以贡献代码，不会编程的可以反馈使用这些工具中的bug、帮着宣传你觉得优秀的项目、star项目⭐️。同时你将学习到更多编程知识、提高自己的编程技巧、发现自己的**兴趣**。

最后[《HelloGitHub》](https://github.com/521xueweihan/HelloGitHub)这个项目就诞生了！😁

---
>**以下为本期内容**｜[点击查看往期内容](https://github.com/521xueweihan/HelloGitHub)

#### Python项目
1、[reddit](https://github.com/reddit/reddit)：[reddit.com](https://www.reddit.com/)网站的源码，通过这个项目，可以学习 python 在构建大型项目中的使用、项目结构、代码风格、python技巧的使用方法等。[安装教程](https://github.com/reddit/reddit/wiki/Install-guide)

![](https://github.com/521xueweihan/HelloGitHub/blob/master/08/img/reddit-show-min.jpg)

2、[httpstat](https://github.com/reorx/httpstat)：httpstat 美化了`curl`的结果，使得结果更加可读。同时它无依赖、兼容Python3、一共才300+行。还可以显示 HTTP 请求的每个过程中消耗的时间，如下图：

![](https://github.com/521xueweihan/HelloGitHub/blob/master/08/img/httpstat-show-min.png)

3、[PyMySQL](https://github.com/PyMySQL/PyMySQL)：纯 pyton 写的 mysql 库，纯 python 的好处就是可以运行在任何装有 python 解释器（CPython、PyPy、IronPython）的平台上。相对于 [MySQLdb](https://github.com/farcepest/MySQLdb1) 性能几乎一样，使用方法也一样，但是** PyMySQL 安装方法极其简单**——`pip install PyMySQL`，PyMySQL 使用示例代码：
```
# 下面为例子需要的数据库的建表语句
CREATE TABLE `users` (
    `id` int(11) NOT NULL AUTO_INCREMENT,
    `email` varchar(255) COLLATE utf8_bin NOT NULL,
    `password` varchar(255) COLLATE utf8_bin NOT NULL,
    PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin
AUTO_INCREMENT=1 ;
```

```python
# -*- coding: utf-8 -*-
import pymysql.cursors

# 连接数据库
connection = pymysql.connect(host='localhost',
                             user='user',
                             password='passwd',
                             db='db',
                             charset='utf8mb4',
                             cursorclass=pymysql.cursors.DictCursor)

try:
    with connection.cursor() as cursor:
        # 创建一个新的纪录（record）
        sql = "INSERT INTO `users` (`email`, `password`) VALUES (%s, %s)"
        cursor.execute(sql, ('webmaster@python.org', 'very-secret'))

    # 连接不会自动提交，所以你想下面要调用 commit 方法，存储对数据库的改动
    connection.commit()

    with connection.cursor() as cursor:
        sql = "SELECT `id`, `password` FROM `users` WHERE `email`=%s"
        cursor.execute(sql, ('webmaster@python.org',))

        # 获取一条的纪录（record）
        result = cursor.fetchone()
        print(result)  # 结果输出：{'password': 'very-secret', 'id': 1}
finally:
    connection.close()  # 操作完数据库一要记得调用 close 方法，关闭连接
```

#### Go项目
4、[kcptun](https://github.com/xtaci/kcptun)：也许是世界上最快的UDP传输工具，支持 macOS/Linux/Windows/FreeBSD/ARM/Raspberry Pi/OpenWrt。

![](https://github.com/521xueweihan/HelloGitHub/blob/master/08/img/kcptun-show-min.png)

#### Ruby项目
5、[discourse](https://github.com/discourse/discourse)：Ruby 语言写的论坛，百分之百开源、免费。

![](https://github.com/521xueweihan/HelloGitHub/blob/master/08/img/discourse-show-min.png)

#### Javascript项目
6、[WeFlow](https://github.com/weixin/WeFlow)：微信出品的一个高效、强大、跨平台的 Web 前端开发工作流工具，[官网](https://weflow.io/)：

![](https://github.com/521xueweihan/HelloGitHub/blob/master/08/img/weflow-show-min.jpeg)

7、[atrament.js](https://github.com/jakubfiala/atrament.js)：极小的Js画板，[在线演示](http://fiala.uk/atrament.js/demo/)

#### C、C++项目
8、[libco](https://github.com/Tencent/libco)：libco 是微信后台大规模使用的 c/c++ 协程库，2013年至今稳定运行在微信后台的数万台机器上。
- 无需侵入业务逻辑，把多进程、多线程服务改造成协程服务，并发能力得到百倍提升;

- 支持CGI框架，轻松构建web服务(New);

- 支持gethostbyname、mysqlclient、ssl等常用第三库(New);

- 可选的共享栈模式，单机轻松接入千万连接(New);

- 完善简洁的协程编程接口
    - 类pthread接口设计，通过co_create、co_resume等简单清晰接口即可完成协程的创建与恢复；
    - \_\_thread的协程私有变量、协程间通信的协程信号量co_signal (New);
    - 语言级别的lambda实现，结合协程原地编写并执行后台异步任务 (New);
    - 基于epoll/kqueue实现的小而轻的网络框架，基于时间轮盘实现的高性能定时器;

#### C#项目
9、[Newtonsoft.Json](https://github.com/JamesNK/Newtonsoft.Json)：Newtonsoft.Json 是一款 .NET 平台中开源的 JSON 序列化和反序列化类库，示例代码：
```C#
public class Account
{
    public string Email { get; set; }
    public bool Active { get; set; }
    public DateTime CreatedDate { get; set; }
    public IList<string> Roles { get; set; }
}

Account account = new Account
{
     Email = "james@example.com",
     Active = true,
     CreatedDate = new DateTime(2013, 1, 20, 0, 0, 0, ateTimeKind.Utc),
     Roles = new List<string>
     {
         "User",
         "Admin"
    }
};

string json = JsonConvert.SerializeObject(account, Formatting.Indented);
// {
//   "Email": "james@example.com",
//   "Active": true,
//   "CreatedDate": "2013-01-20T00:00:00Z",
//   "Roles": [
//     "User",
//     "Admin"
//   ]
// }

Console.WriteLine(json);
```

#### Objective-C、Swift项目
10、[aria2gui](https://github.com/yangshun1029/aria2gui)：Aria2 的 Mac 客户端（下载工具），[介绍、使用方法](http://www.jianshu.com/p/1290f8e7b326)，特点：
- 集成了 aria2，运行后即完成配置工作
- 多线程下载
- 未完成任务退出可以自动保存
- 支持迅雷离线，百度，115，360等网盘的aria2导出（需要浏览器插件支持）
- 支持PT/BT，BT速度跟种子热度有关，如果没有速度网盘离线后再下载
- 在Badge显示整体下载速度
- 任务完成通知

![](https://github.com/521xueweihan/HelloGitHub/blob/master/08/img/aria2gui-show-min.png)

#### Java项目
11、[AndroidUtilCode](https://github.com/Blankj/AndroidUtilCode)：Android 开发人员不得不收集的代码，[中文介绍](https://github.com/Blankj/AndroidUtilCode/blob/master/README-CN.md)

12、[DanmakuFlameMaster](https://github.com/Bilibili/DanmakuFlameMaster)：Bilibili 开源的，Android 开源弹幕引擎·烈焰弹幕使，特性：
- 使用多种方式(View/SurfaceView/TextureView)实现高效绘制
- B站xml弹幕格式解析
- 基础弹幕精确还原绘制
- 支持mode7特殊弹幕
- 多核机型优化，高效的预缓存机制
- 支持多种显示效果选项实时切换
- 实时弹幕显示支持
- 换行弹幕支持/运动弹幕支持
- 支持自定义字体
- 支持多种弹幕参数设置
- 支持多种方式的弹幕屏蔽

#### 其它
13、[提问的智慧](https://github.com/FredWe/How-To-Ask-Questions-The-Smart-Way/blob/master/README-zh_CN.md)

14、[jstraining](https://github.com/ruanyf/jstraining)：阮一峰，全栈工程师培训材料

15、[PTVS](https://github.com/Microsoft/PTVS)：Visual Studio 下的 python 开发工具

16、[the-swift-programming-language-in-chinese](https://github.com/numbbbbb/the-swift-programming-language-in-chinese)：中文版 Apple 官方 Swift 教程《The Swift Programming Language》

17、[styleguide](https://github.com/fex-team/styleguide)：百度前端研发团队的文档与源码编写风格

18、[weex](https://github.com/alibaba/weex)：移动端，跨平台前端框架，[详细的中文档](https://github.com/weexteam/article/wiki/Weex中文文档)

19、[macOS-Security-and-Privacy-Guide](https://github.com/drduh/macOS-Security-and-Privacy-Guide)：A practical guide to securing macOS.（英文）

---


## 声明
如果你发现了好玩、有意义的开源项目，[点击这里](https://github.com/521xueweihan/HelloGitHub/issues/new)分享你觉得有意思的项目。

- 分享项目格式：项目名称——项目地址：项目描述(中文)，追求完美👉项目上手demo、有图有真相～

或许你分享的项目会让别人由衷的感慨：“原来还有这么有意思的项目！编程可以这么酷！”

欢迎转载，请注明出处和作者，同时保留声明和联系方式。

## 联系方式
- GitHub：[削微寒](https://github.com/521xueweihan)

- 博客园：[削微寒](http://www.cnblogs.com/xueweihan/)

- 邮箱：595666367@qq.com
