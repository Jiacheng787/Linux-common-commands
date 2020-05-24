给自己参考用，更新中～

*   [1.shell操作](##1.shell操作)
*   [2.文件操作](##2.文件操作)
*   [3.Linux命令-网络和系统](##3.Linux命令-网络和系统)

## 1.shell操作

    查看系统当前使用的shell
    echo $SHELL
    查看是否安装zsh
    cat /etc/shells
    切换shell为zsh
    chsh -s /bin/zsh
    连接远程服务器
    ssh admin@hhlnyfz.com
    断开连接
    logout && exit && Ctrl+D

>bash & zsh  
>命令行开发者工具

## 2.文件操作

    cd     进入目录（也可以直接输入目录名）
    cd ~   进入根目录
    cd ..  返回上级目录
    ls     查看目录下的文件
    ls -a  查看隐藏文件
    vi     编辑文件（按i进入insert模式，esc退出，shift+: wq保存）
    cat    查看文件
    mkdir  创建目录
    touch  创建文件操作
    rm     删除
    pwd    显示当前操作的路径
    tree   以目录树方式显示文件架构
    
## 3.Linux命令-网络和系统

    1) ping命令-测试网络连通性
       Windows系统
       ping hhlnyfz.com
       Linux需要指定执行次数
       ping -c 3 hhlnyfz.com
       只看结果不看过程
       ping -q -c 3 hhlnyfz.com
       指定ping的数据包的大小（默认64字节）
       ping -s 65500 -c 3 hhlnyfz.com
       指定ping的时间间隔（默认1秒）
       ping -i 0.1 -c 3 hhlnyfz.com
       Flood Ping（潮水模式的ping）
       ping -f -c 100 192.168.0.29
       Flood ping无间隔方式全力发送数据包，每秒钟至少发送100个，如果丢包率为0，说明网卡工作正常，也没有任何网络拥塞。
    2) 域名解析
       DNS服务器和域名解析
       nslookup www.hhlnyfz.com
    3) nc命令
       聊天软件
       服务端命令：nc -1 12345（-1选项监听12345端口）
       客户端命令：nc 116.255.245.207 12345（指定IP和端口）
       任何一端执行组合键Ctrl+D断开连接
       端口扫描
       nc -z -v -n -w 2 127.0.0.1 20-23
       扫描本地20-23e端口
       传输文件
       服务端（发送端）：nc -v -1 12345 < book_out.txt
       客户端（接收端）：nc -v -n 116.255.245.207 12345 > book_in.txt
                       ls -hl book_in.txt
       服务端（接收端）：nc -v -1 12345 > book_in.txt
       客户端（发送端）：nc -n 116.255.24.207 12345 < book_out.txt
    4) ssh-copy-id无密码登录
    5) uptime命令
    6) shutdown命令
       [Linux shutdown 命令详解](https://blog.csdn.net/u013982161/article/details/52663466)
       
