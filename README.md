今天主要讲一下找发消息的call，首先分析，正常发消息，至少需要两个参数：一个是wxid，一个是要发送的内容。需要用到的工具，OD和CE。找发消息要点：可以从这个发消息的内容入手，还有一点，我发给谁。比如我发给文件助手，文件助手的wxid是：filehelper，
用CE找，如下图：当前聊天窗口是文件助手，然后再切换到某个好友的微信聊天窗口，搜索：wxid_，然后再切换回去文件助手聊天窗口，

![image](https://user-images.githubusercontent.com/96330669/163746771-e8202758-9935-4c57-b3ed-ca4e7a206c5e.png)

将搜到的信息，移到最下面，切换不同的聊天窗口，双击下面的value值，可以看到不同的wxid，然后把value值里面的wxid修改成其他好友的wxid，这个时候发消息，看到消息没有发送到当前人的，而是发送给被修改wxid的那个好友了。也就是说，wxid是谁，就发给谁了，不管当天聊天窗口是谁。

![image](https://user-images.githubusercontent.com/96330669/163746800-55d9fcb8-df37-49f3-b10e-6e09997ab82f.png)

然后从上面的找到地址，去OD里面下一个内存访问断点，然后在微信发送一条消息，这时就断下来了；

![image](https://user-images.githubusercontent.com/96330669/163746816-ec22ff0e-9589-49d8-9adf-6f3bfab46254.png)

然后把刚才的断点删除，找传两个或者以上参数的汇编的地方，下一个断点，再发消息，看断下来。最终找到这个发消息call的地址。

目前已经实现了很多有趣的功能，运行稳定，比如：发各种消息，
接收各种消息，群管，下载文件，加好友，检测僵尸粉，朋友圈等等功能，
可提供接口，方便各种语言二次开发，欢迎技术交流，Q：2645542961
，请勿用于商业用途。

![image](https://user-images.githubusercontent.com/96330669/163746925-98b2b76e-1d80-473e-ab88-8db198699aea.png)

