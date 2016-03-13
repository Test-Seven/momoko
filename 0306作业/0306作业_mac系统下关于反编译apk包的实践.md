
#mac系统下关于反编译apk包的实践
##1.工具准备
>操作系统：mac
>
>apktool
>
>dex2jar
>
>jd-gui
>

###1.1 apktool
google了一下，官方是这么说的
![](http://7xrgej.com1.z0.glb.clouddn.com/apk%E5%8F%8D%E7%BC%96%E8%AF%914FC03375-C19F-468F-8AA8-C3388793E47F.jpg)
操作比较麻烦，而且本人还遇到了坑，反正是没有操作成功。后来我试着用 

    brew install apktool
这个命令，瞬间安装成功：
![](http://7xrgej.com1.z0.glb.clouddn.com/apk%E5%8F%8D%E7%BC%96%E8%AF%9101BA71F6-EAA8-491D-AAF2-E49DFB94B3FA.jpg)
所以说brew install是个好东西……
    为了证明apktool可以使用，马上反编译了一下，步骤如下：
>>1.建立一个名叫apk的文件夹
>>
>>2.将目标apk文件放入这个apk文件夹中
>>
>>3.在终端通过命令行进入apk文件夹下，运行以下命令
>>
    

    apk d XXXX.apk
反编译成功： 
![](http://7xrgej.com1.z0.glb.clouddn.com/apk%E5%8F%8D%E7%BC%96%E8%AF%917D2F3B82-8B9D-4BAB-90FE-858C706870D9.jpg)

###1.2 dex2jar
安装方法同上
    
    brew install dex2jar
    
###1.3 jd-gui
这个文件在使用brew install命令安装时报错了，找不到匹配的文件。（brew也不是万能哈），于是直接google到官网下载，解压安装。么有遇到坑。

##2.apk包的反编译和回编译
>相关概念
>
>>反编译
>>
>>回编译
>>

###反编译操作
反编译在安装成功apktool之后就已经操作过，反编译成功后再apk文件夹下，会生成一个和包名一样的新的文件夹，即反编译出的文件夹，回编译是在这个文件夹基础之上进行的操作。
回编译命令如下：

    apktool b XXXX(反编译后得到的文件夹名称)
运行成功：

![](http://7xrgej.com1.z0.glb.clouddn.com/apk%E5%8F%8D%E7%BC%96%E8%AF%91EBC8918B-DB7D-4E60-B5A2-292037A214B1.jpg)

得到文件夹内容更新如下：
![](http://7xrgej.com1.z0.glb.clouddn.com/apk%E5%8F%8D%E7%BC%96%E8%AF%914B812E8C-A29C-4C08-B6F2-3FC174C4D8BB.jpg)

###用dex2jar将class.dex转化成jar包
打开终端，进入到dex2jar目录下，运行如下命令：

    ./d2j-dex2jar.sh /Users/liteng/Desktop/apk/miaopai_live_2.0.1_37867/build/apk/classes.dex
即：
  
    ./d2j-dex2jar.sh 绝对路径/classes.dex
    
此时报错，/d2j-dex2jar.sh脚本没有执行权限，对其进行权限修改：
 
    chmod +x d2j-dex2jar.sh
    
之后再进行上一步转化操作，如图所示：

![](http://7xrgej.com1.z0.glb.clouddn.com/apk%E5%8F%8D%E7%BC%96%E8%AF%9102536134-70BE-45D5-8AB4-62369D275774.jpg)

###将dex2jar目录下的到的class.dex的jar包放入JD-GUI中
如图所示：
![](http://7xrgej.com1.z0.glb.clouddn.com/apk%E5%8F%8D%E7%BC%96%E8%AF%91680AA6A4-0C4C-4134-B006-6F0D375C8DFC.jpg)
