###### 配置IP:

进入系统视图
`system-view`
进入 GigabitEthernet 1/0 接口视图
`interface GigabitEthernet 1/0`
为接口GigabitEthernet 1/0 配置IP地址。23是子网掩码，255.255.254.0也行
`ip address 你的IP地址 23`
退出GigabitEthernet 1/0 接口视图，回到系统视图
`quit`
进入VTY用户线类视图
`line vty 0 63`
设置登录用户的认证方式 none ，就是不需要认证
`authentication-mode none`
设置用户的权限 network-admin为最大权限，类似Linux 777
`user-role network-admin`
设置连接超时时间
`idle-timeout 35000 0`
退出VTY用户线类视图
`quit`
设置静态路由
`ip route-static 10.0.0.0 8 10.99.210.1`
开启VSR设备的Telnet服务，启用之后才可以使用telnet远程登陆
`telnet server enable`
保存配置
`save`

然后使用mobaxterm 创建telnet连接就可以连上自己的VSR了



###### 配置VSR发送日志到linux主机

(1)Device上的配置

开启信息中心功能。
```
<Device> system-view
[Device] info-center enable
```

配置发送日志信息到IP地址为10.99.210.206的日志主机，端口默认514，日志主机记录工具为local5。
`[Device] info-center loghost 10.99.210.206 facility local5`

(注，查看sa南向ip在【系统】/【部署管理】/【智能分析引擎】)

配置输出规则：允许default(所有)模块、等级高于等于informational的日志信息输出到日志主机。
`[Device] info-center source default loghost level informational`

(2)日志主机上的配置

编辑/etc/路径下的文件rsyslog.conf，添加以下内容。
```
$ModLoad imudp
$UDPServerRun 514
```
```
Device configuration messages
local5.info /var/log/Device/info.log 
```

查看系统守护进程rsyslogd的进程号，中止rsyslogd进程，并重新在后台启动rsyslogd，使修改后配置生效。
`ps -ae | grep rsyslogd`
`147`
`kill 147`
`systemctl restart rsyslog.service   # 或者service rsyslog restart`

进行以上操作之后，系统就可以在相应的文件中记录日志信息了。


一个网络中配置重复ip

配置 2/0口的ip地址
查看ip信息
`sys`
`dis int br`

`int GigabitEthernet 2/0`
`undo ip address 112.40.40.5 24`
`ip address 112.40.40.4 24`

查看info-center相关配置
`disp current-configuration  | include  info-center`




