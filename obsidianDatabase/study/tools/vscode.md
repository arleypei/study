
### SSH连接ubuntu
---
1. ubunut安装软件工具**openssh-server**
	`sudo apt-get install openssh-server`
2. 启动ssh服务
	`sudo systemctl start ssh`
3. 查看ssh服务是否开启
	执行`ps -ef | grep ssh`，查看sshd服务存在
	![[Pasted image 20241103145823.png]]
4. vscode安装**Remote - SSH**插件
	![[Pasted image 20241103150146.png]]
5. 编辑ssh config文件
	![[Pasted image 20241103151446.png]]
6. 连接linux
	在新窗口打开连接
	![[Pasted image 20241103151638.png]]
	选择linux
	![[Pasted image 20241103151703.png]]
	输入linux用户密码
	![[Pasted image 20241103151727.png]]
	连接成功
	![[Pasted image 20241103151834.png]]

### SSH连接ubuntu免密设置
---
由于每次连接都要输入密码，比较麻烦，所以最好设置免密连接
1. Windows生成公钥
	打开cmd，执行命令`ssh-keygen`，遇到选择直接回车
	![[Pasted image 20241103152351.png]]
2. Windows查看公钥
	私钥和公钥在目录`C:\Users\用户名\.ssh`，分别是`id_rsa`和`id_rsa.pub` 
	打开`id_rsa.pub`，复制全部内容
	![[Pasted image 20241103152650.png]]
3. linux查看.ssh文件
	执行`ll`命令查看主目录下是否有`.ssh`文件，如果没有，执行`makir .ssh`命令创建该文件夹
	![[Pasted image 20241103153211.png]]
4. linux创建`authorized_keys`文件
	执行`vim ~/.ssh/authorized_keys`，如果已有则修改该文件（如果没有，vim会自动创建该文件）
	将Windows复制的公钥信息粘贴到`authorized_keys`文件
	![[Pasted image 20241103153449.png]]
	如果是手动创建的.ssh目录和authorized_keys文件，需要将其权限分别修改为700和600
	```
	chmod 700 ~/.ssh
	chmod 600 ~/.ssh/authorized_keys
	```