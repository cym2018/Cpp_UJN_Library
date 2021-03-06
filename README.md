# Cpp_UJN_Library
###### _用C++写的济南大学图书馆座位预约程序,你没见过的船新版本_


早上定了八个闹钟,喜欢的位置还是被别人抢走了?

用多个账号占座,一不留神就失约?

Python脚本,看不懂,不会用,版本不兼容?
## 看到这里,你来对了
Cpp_UJN_Library:一个可以在Windows系统下预约座位的程序.
###### 重要提示:程序预约的是★第二天★的座位!
# 怎么用?
## 使用前
#### 运行环境
Windows All
#### 获取
为了防止莫名其妙的错误,32位,64位,Debug版,Release版都上传了,推荐程度从前往后递减,不能运行,就换一个试试

预约: [Release_64](https://github.com/cym2018/Cpp_UJN_Library/raw/master/File/Library_Release_X64.exe) [Release_32](https://github.com/cym2018/Cpp_UJN_Library/raw/master/File/Library_Release_X32.exe) [Debug_64](https://github.com/cym2018/Cpp_UJN_Library/raw/master/File/Library_Debug_X64.exe) [Debug_32](https://github.com/cym2018/Cpp_UJN_Library/raw/master/File/Library_Debug_X32.exe) 

签到: [Release_64](https://github.com/cym2018/Cpp_UJN_Library/raw/master/File/Checkin_Release_X64.exe) [Release_32](https://github.com/cym2018/Cpp_UJN_Library/raw/master/File/Checkin_Release_X32.exe) [Debug_64](https://github.com/cym2018/Cpp_UJN_Library/raw/master/File/Checkin_Debug_X64.exe) [Debug_32](https://github.com/cym2018/Cpp_UJN_Library/raw/master/File/Checkin_Debug_X32.exe) 
## 使用时
#### 打开Library.exe所在的文件夹,新建文本文档,命名为"data.txt".
#### 打开data.txt,按照以下格式填写
###### 重要提示:data.txt内不能有空格,空行,否则会出错!
```
第1行:此行不会对程序的运行产生任何影响,用于保存预约信息的中文描述(换句话说,这行是给人看的,类似于书签)
第2行:学号
第3行:密码
第4行:座位id  (参见"获取座位id的方法")
第5行:开始时间(单位:分钟)
第6行:结束时间
第7行开始填写第2个预约信息,以此类推.
```
[_获取座位id的方法_](http://www.cym2019.xyz/library.jsp)

看不懂?[点我](https://github.com/cym2018/Cpp_UJN_Library/blob/master/README.md#datatxt样例)

填写完data.txt,双击运行library.exe,程序将会遍历每个预约信息.

运行结果可以在log.txt查看.

这就是程序所有的功能了.

但是,如果你~~早上起不来~~学习太忙,那么,往下看:
## 进阶篇——自动运行
###### 以新建每天早上5:00:30自动执行library.exe的计划任务为例.
```
1.单击开始菜单或键盘上的Windows键
2.输入"任务计划",打开"任务计划程序".
3.单击"任务计划程序库"
4.在右边栏找到"创建任务",单击打开
5.输入名称,描述
6.切换到"触发器"选项卡,单击"新建".
	7.在弹出的窗口中,开始任务,选择"按预定计划".
	8.频率选择"每天",填写时间:05:00:30
	9.选中"重复任务间隔",时间填写"1 分钟",持续时间填写"3 分钟".
	10.单击"确定".
11.切换到"操作"选项卡,单击"新建"
	12."操作"选择"启动程序".
	13.单击"浏览",选中"library.exe",打开
	14.复制程序的路径,删掉文件名,粘贴到"起始于"文本框中
		(如果"程序或脚本"为"C:/programfile/library.exe",则"起始于"为"C:/programfile")
	15.单击"确定"
16.切换到"条件"选项卡
	17.取消"只有在计算机使用交流电源时才启动此任务"
	18.选中"唤醒计算机运行此任务"
19.单击确定
```
###### 重要提示:电脑关机时无法执行计划任务!
## 其他值得注意的信息
#### 关于签到功能
签到需要连接图书馆的wifi"Lib_Student".

近期图书馆离馆禁止遗留物品,无法把电脑单独留在图书馆,所以自动签到功能废了.

当然,如果你习惯带着电脑去图书馆,用这个程序可以省去打开APP签到的麻烦.
###### 如果你有一部闲置的安卓手机,可以试试我的另一个项目[Android_UJN](https://github.com/cym2018/Android_UJN)
#### 日志部分
对~~所有~~多数类型的返回格式自动处理,确保日志文件的可读性.
#### 注明出处
服务器返回内容的格式转换部分来自[zhangxueyang1的文章:c++ utf8与std::string字符编码转换](https://blog.csdn.net/zhangxueyang1/article/details/54178195)

网络编程部分来自[微软文档](https://docs.microsoft.com/zh-cn/windows/desktop/WinSock/windows-sockets-start-page-2)
#### 许可
如被抄袭,诚惶诚恐
## 已知问题
无(~~xie zhe tiao ke yi rang zi ji kai xin,guan ta you mei you wen ti~~)
## 还有
出现任何问题,欢迎发邮件[联系我](cym2018.xyz@qq.com).

PS:~~我写的MySocket类,是真的牛批~~(算了不说了).
# 附录:
###### data.txt样例
```
#这是第一行,学号220161000000,密码123456,座位号23456,开始时间是上午8(*60)点,结束时间是中午12(*60)点
220161000000
123456
23456
480
720
#这是第七行,学号220161000001,密码234567,座位号34567,开始时间是中午12(*60)点,结束时间是下午16(*60)点
220161000001
234567
34567
720
960
```
