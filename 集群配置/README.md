# 集群配置

## 配置步骤

配置`core-site.xml`

```
cd $HADOOP_HOME/etc/hadoop
```

```
<configuration>
	<!-- 指定 NameNode 的地址 -->
	<property>
		<name>fs.defaultFS</name>
		<value>hdfs://hadoop102:8020</value>
	</property>
	<!-- 指定 hadoop 数据的存储目录 -->
	<property>
		<name>hadoop.tmp.dir</name>
		<value>/opt/module/hadoop-3.1.3/data</value>
	</property>
	<!-- 配置 HDFS 网页登录使用的静态用户为 aowei -->
	<property>
		<name>hadoop.http.staticuser.user</name>
		<value>aowei</value>
	<property>
</configuration>
```

配置`hdfs-site.xml`

```
<configuration>
<!-- nn web 端访问地址 -->
	<property>
		<name>dfs.namenode.http-address</name>
		<value>hadoop102:9870</value>
	</property>
	<!-- 2nn web 端访问地址 -->
	<property>
		<name>dfs.namenode.secondary.http-address</name>
		<value>hadoop104:9868</value>
	</property>
</configuration>
```

配置`yarn-site.xml`

```
<configuration>
	<!-- 指定MR 走shuffle-->
	<property>
		<name>yarn.nodemanager.aux-servicces</name>
		<value>mapreduce_shuffle</value>
	</property>
	
	<!-- 指定ResourceManager的地址 -->
	<property>
		<name>yarn.resourcemanager.hostname</name>
		<value>hadoop103</value>
	</property>
	
	<!-- 环境变量的继承 -->
	<property>
		<name>yarn.nodemanager.env-whitelist</name>
		<value>JAVA_HOME,HADOOP_COMMON_HOME,HADOOP_HDFS_HOME,HADOOP_CONF_DIR,CLASSPATH_PREPEND_DISTCACHE,HADOOP_YARN_H OME, HADOOP_MAPRED_HOME</value>
	</property>
</configuration>
```

配置`mapred-site.xml`

```
<configuration>
	<!-- 指定MapReduce 程序运行在Yarn上 -->
	<property>
		<name>mapreduce.framework.name</name>
		<value>yarn</value>
	</property>
</configuration>
```

