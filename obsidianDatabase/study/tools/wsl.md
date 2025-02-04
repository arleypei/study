迁移磁盘
```
关闭wsl,查看wsl状态
wsl --shutdown
wsl -l -v
导出ubuntu压缩包
 wsl --export Ubuntu-20.04 D:\wsl\ubuntu\Ubuntu.tar
注销原ubuntu
wsl --unregister Ubuntu-20.04
导入ubuntu
wsl --import Ubuntu-20.04 D:\wsl\ubuntu\ D:\wsl\ubuntu\Ubuntu.tar
设置默认用户
Ubuntu2004 config --default-user pal
```







