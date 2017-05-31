* 查找文件  
    * `find / -name filename.txt` 根据名称查找`/`目录下的`filename.txt`文件
    * `find . -name "*.xml"` 递归查找所有的`xml`文件
    * `find . -name "*.xml" | xargs grep "hello world"` 递归查找所有文件内容中包含`hello world`的`xml`文件
    * `find ./ -size 0 | xargs rm -f &` 删除文件大小为零的文件
    * `ls -l | grep 'jar'` 查找当前目录中的所有`jar`文件
    * `grep 'test' d*` 显示所有以`d`开头的文件中包含`test`的行。
    * `grep 'test' aa bb cc`显示在`aa`，`bb`，`cc`文件中匹配`test`的行。
    * `grep '[a-z]{5}' aa`显示所有包含每个字符串至少有`5`个连续小写字符的字符串的行
* 查看一个程序是否运行
    * `ps –ef|grep tomcat` 查看所有有关`tomcat`的进程
* 终止线程
    * `kill -9 19979` 终止线程号位`19979`的线程  
* 查看文件，包含隐藏文件
    * `ls -al`
* 当前工作目录
    * `pwd`
* 复制文件
    * `cp source dest` 复制文件
    * `cp -r sourceFolder targetFolder` 递归复制整个文件夹
    * `scp sourecFile romoteUserName@remoteIp:remoteAddr` 远程拷贝
* 创建目录
    * `mkdir newfolder`
* 删除目录
    * `rmdir deleteEmptyFolder` 删除空目录 
    * `rm -rf deleteFile` 递归删除目录中所有内容
* 移动文件
    * `mv /temp/movefile /targetFolder`
* 重命令
    * `mv oldNameFile newNameFile`
* 切换用户
    * `su -username`
* 修改文件权限
    * `chmod 777 file.java//file.java` 的权限 `-rwxrwxrwx`，`r`表示读、`w`表示写、`x`表示可执行
* 压缩文件
    * `tar -czf test.tar.gz /test1 /test2`
* 列出压缩文件列表
    * `tar -tzf test.tar.gz`
* 解压文件
    * `tar -xvzf test.tar.gz`
* 查看文件头10行
    * `head -n 10 example.txt`
* 查看文件尾10行
    * `tail -n 10 example.txt`
* 查看日志类型文件
    * `tail -f exmaple.log//`这个命令会自动显示新增内容，屏幕只显示`10`行内容的（可设置）
* 使用超级管理员身份执行命令
    * `sudo rm a.txt`使用管理员身份删除文件
* 查看端口占用情况
    * `netstat -tln | grep 8080`查看端口`8080`的使用情况
* 查看端口属于哪个程序
    * `lsof -i :8080`
* 查看进程
    * `ps aux | grep java` 查看`java`进程
    * `ps aux` 查看所有进程
* 以树状图列出目录的内容
    * `tree a`
* 文件下载
    * `wget http://file.tgz`
    * `curl http://file.tgz`
* 网络检测
    * `ping www.taobao.com`
* 远程登录
    * `ssh userName@ip`
* 打印信息
    * `echo $JAVA_HOME` 打印`java home` 环境变量的值
