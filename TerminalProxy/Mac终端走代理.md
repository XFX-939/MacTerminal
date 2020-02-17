在安装brew的时候，无论如何都连不上服务器，后来在他人的指点下，了解到了终端代理的操作。

一开始以为不管是ssr还是v2ray，只要开了全局代理，那么终端也是走的外网。实际上这个想法时错误的，终端连外网，仍然需要另外操作。



1. ### 启动shadowsocks

   在ssr高级设置中，查看socks5的监听地址与端口，并记录下来。

   ![ssr高级设置](https://github.com/XFX-939/MacTerminal/blob/master/TerminalProxy/ssr%E9%AB%98%E7%BA%A7%E8%AE%BE%E7%BD%AE.png)

2. ### 修改zshrc

   ```shell
   vim ～/.zshrc
   ```

   “～ ” 你的home目录，在OS X下位于/Users/你的用户名/

   “.” 类unix下的隐藏文件，文件名带"."之后在GUI文件管理器和ls的默认设置下不会显示出来，使用ls －a命令可以显示出这些文件。

   zshrc是一个文件，准确的说这个文件的文件名是".zshrc".
   综上所述，这就是个配置文件的路径而已。

3. ### 设置proxy list

   ```shell
   alias proxy='export all_proxy=socks5://127.0.0.1:1086'
   
   alias unproxy='unset all_proxy'
   ```

   

4. ### source一下zshrc

   ```shell
   source ～/.zshrc
   ```

5. ### 查看一下当前ip

   ```shell
   curl cip.cc
   ```

   开启代理

   ```shell
   proxy
   ```

   对比一下ip

   ```shell
   curl cip.cc
   ```

6. ### 关闭代理

   ```shell
   unproxy
   ```

   

 ![完整操作截图](https://github.com/XFX-939/MacTerminal/blob/master/TerminalProxy/%E5%AE%8C%E6%95%B4%E6%93%8D%E4%BD%9C%E6%88%AA%E5%9B%BE.png)

