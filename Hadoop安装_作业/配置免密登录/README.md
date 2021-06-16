# ssh配置免密登录

## 配置步骤

切换到用户目录下，生成公钥与私钥

```
cd .ssh
ssh-keygen -t rsa
三次回车
```

将公钥拷贝到其他主机

```
ssh-copy-id hadoop103
ssh-copy-id hadoop104
ssh-copy-id hadoop102
```

显示主机名

```
hostname
```

