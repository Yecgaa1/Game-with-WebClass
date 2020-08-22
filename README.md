# 想在一台电脑好好学知识又想···打游戏

## 开始

**请注意，这个程序不追求性能，只是追求完成目标**



这个问题的初衷已经很详细的描述在标题上了

所以怎么办呢？

我手上有两个屏幕，一边拿来玩游戏，一边拿来看网络教学视频不美哉？

问题是游戏声音太大了，盖过了视频声音

游戏是彩虹六号，属于全屏幕游戏，鼠标会一直焦点在游戏上，所以只能考虑怎么用键盘完成播放的事情了

思路就是：按一次，关游戏声音，在chrome顺带播放

再按一次就正好反过来



## 声音

我找了很久，详情见此文

然后问题突然简单得让我不敢相信了

```python
import pycaw
```



## 快捷键

监听键盘不就好了

```python
import keyboard
```

[参考用法]: https://www.jianshu.com/p/8e508c6a05ce

播放视频就直接模拟按键盘上的媒体播放键就好了

## 最终完成·····了吗？？？

你想多了，整个程序用时1天左右，然而这才刚刚过了一个小时

彩虹六号的反作弊系统似乎会阻止一切外界程序模拟键盘

（但是当时我还未完全证明这一点）

首先是监听上，没把彩六放前台就全局都可以

就彩六不是全局

我尝试了keyboard库

你觉得这个库不够底层？ctypes.windll.user32底层dll用RegisterHotKey注册够了吧？

答案是不行

所以···

## 请求配合手机完成

通讯上直接用socket的tcp完成

app编程用appinventor快速写完，调试

很顺利就成功控制了音量

然后终于发现也不能模拟按媒体键

想到了用**selenium控制浏览器**，寻找元素，用click()

我推测selenium是通过浏览器底层驱动实现，所以应该没问题

是的，它能用

终于，达到了我想要的效果了···

## 有关源代码

最终音量控制程序服务端：

[HearClass]: https://github.com/Yecgaa1/Game-with-WebClass/blob/master/HearClass%E5%AE%8C%E5%85%A8%E5%8F%AF%E7%94%A8.py

手机客户端：

[apk]: https://github.com/Yecgaa1/Game-with-WebClass/blob/master/study1.1.apk

在该目录下还有一些失败的（彩六外可用）程序代码：

[项目地址]: https://github.com/Yecgaa1/Game-with-WebClass



## 附录

使用了AppInventor中Jean-Rodolphe_Letert开发的的[TCP/IP Extension](https://community.appinventor.mit.edu/t/tcp-ip-extension/7142)插件，一如既往的好用

