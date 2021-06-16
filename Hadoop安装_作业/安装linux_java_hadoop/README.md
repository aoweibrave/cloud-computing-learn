# cloud-computing-learn

## 安装步骤

安装`vm ware` 虚拟机

最小化安装三台`Centos7`

设置主机名：`hodoop102`，`hadoop103`，`hadoop104`

设置静态`ip`：`192.168.10.102`，`192.168.10.103`，`192.168.10.104`

安装`Java`，`hadoop`

## 配置环境变量

新建自己的环境配置文件`my_env.sh`

```
sudo vim /etc/profile.d/my_env.sh
```

配置如下环境变量

```
#JAVA_HOME
export JAVA_HOME=/opt/jdk1.8.0_231
export JRE_HOME=${JAVA_HOME}/jre
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib
export PATH=.:${JAVA_HOME}/bin:$PATH

#HADOOP_HOME
export HADOOP_HOME=/opt/hadoop-3.1.4

export PATH=$PATH:$HADOOP_HOME/bin
export PATH=$PATH:$HADOOP_HOME/sbin
```

使环境变量生效

```
source /etc/profile
```

## 配置网络

```
vim /etc/sysconfig/network-scripts/ifcfg-ens33
```

关闭防火墙：

```
systemctl stop firewalld
```

关闭开机启动防火墙

```
systemctl disable firewalld.service
```

