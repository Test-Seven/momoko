#calabash-android环境搭建
先尝试直接运行安装命令
    
      gem install calabash-android
结果报错，如下图：
![](http://7xrgej.com1.z0.glb.clouddn.com/%E6%B7%98%E5%AE%9D%E9%95%9C%E5%83%8FEC41D1CA-32A4-49A1-93C9-5A21A559F342.jpg)
估计是淘宝镜像出了问题，直接用了浏览器打开网址 http://ruby.taobao.org
![](http://7xrgej.com1.z0.glb.clouddn.com/%E6%B7%98%E5%AE%9D%E9%95%9C%E5%83%8F677CDB6F-D9EB-44F6-8303-84B568859777.jpg)
参照说明运行命令：
![](http://7xrgej.com1.z0.glb.clouddn.com/%E6%B7%98%E5%AE%9D%E9%95%9C%E5%83%8FC8B146D5-54CF-4EBC-BA5F-2FFCE0098349.jpg)
运行结果：
![](http://7xrgej.com1.z0.glb.clouddn.com/%E6%B7%98%E5%AE%9D%E9%95%9C%E5%83%8F1A2FA55D-DD03-416D-956A-83A06DD8F343.jpg)
不是特别明白到底弄好了没有，尝试再次去安装一下calabash-android，继续运行如下命令：

    gem install calabash-android
    
运行结果如下：
![](http://7xrgej.com1.z0.glb.clouddn.com/%E6%B7%98%E5%AE%9D%E9%95%9C%E5%83%8F5A7E5A3B-5EA2-4071-8D07-E530F07E0266.jpg)
我猜测应该是成功了，之所以老报错无法从http://ruby.taobao.org/下载资源是因为淘宝镜像官网声明了：
**已经停止基于 HTTP 协议的镜像服务, 请在配置中使用 HTTPS 协议代替**
![](http://7xrgej.com1.z0.glb.clouddn.com/%E6%B7%98%E5%AE%9D%E9%95%9C%E5%83%8FAC51730E-7320-4316-A227-5F9B6FB02794.jpg)

#创建features文件夹
执行如下命令

     calabash-android gen
结果如下：
![](http://7xrgej.com1.z0.glb.clouddn.com/%E6%B7%98%E5%AE%9D%E9%95%9C%E5%83%8F0BF72A9B-897F-4255-8735-33E04145EB59.jpg)
此时，当前目录中生成了features的文件，进入查看目录结构：
![](http://7xrgej.com1.z0.glb.clouddn.com/%E6%B7%98%E5%AE%9D%E9%95%9C%E5%83%8FEC9EE846-25DD-463E-BE16-DD8977C4A0CD.jpg)

