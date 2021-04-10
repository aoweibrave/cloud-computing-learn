# 启动集群_测试

## 配置workers

```
vim /opt/hadoop-3.1.4/etc/hadoop/workers

hadoop102
hadoop103
hadoop104
```



```
sudo scp /opt/hadoop-3.1.4/etc/hadoop/workers root@hadoop103:/opt/hadoop-3.1.4/etc/hadoop/workers
```

初始化文件系统

```
hdfs namenode -format
```



```
sbin/start-dfs.sh
```



```
sbin/start-yarn.sh
```

