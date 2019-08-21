### MacOS 生成SSHKey

- 查看本机存不存在SSHKey
````
MacBook-Pro:~ LeoShi$ ls -al ~/.ssh
------------------------------
ls: /Users/leoshi/.ssh: No such file or directory
````

- 生成SSHKEY

>your_full_name@xxxxx.com 你需要生成的邮箱地址

````
-----命令格式-------------------------
ssh-keygen -t rsa -C "your_full_name@xxxxx.com"
````
````
MacBook-Pro:~ LeoShi$ ssh-keygen -t rsa -C "LeoShi@example.com"        
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/LeoShi/.ssh/id_rsa): 
Created directory '/Users/LeoShi/.ssh'.
-----是否需要秘钥密码-------------------------
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
-----秘钥生成路径-------------------------
Your identification has been saved in /Users/LeoShi/.ssh/id_rsa.
Your public key has been saved in /Users/LeoShi/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:o3Q/KkAammksynlPW/CGqU3s/ELSQjEdCZ+UZb6b7Ps LeoShi@example.com
The key's randomart image is:
+---[RSA 2048]----+
|   .oo=o         |
|   oo++          |
|    oo .         |
|  ...   .        |
|.+.+....S        |
|=o.oo+*ooo       |
|= . +B.B  o      |
|.o .B.*  . .     |
|  ...*o=+E       |
+----[SHA256]-----+
````
- 验证是否生成
````
MacBook-Pro:~ LeoShi$ ls -al ~/.ssh                          
total 16
drwx------   4 LeoShi  staff   128 Aug 21 11:17 .
drwxr-xr-x+ 21 LeoShi  staff   672 Aug 21 11:16 ..
-----下面两个文件代表生成成功-------------------------
-rw-------   1 LeoShi  staff  1823 Aug 21 11:17 id_rsa
-rw-r--r--   1 LeoShi  staff   398 Aug 21 11:17 id_rsa.pub
````

- .pub文件就是你在其他网站使用的SSHKey的公钥
````
LeoShideMacBook-Pro:~ LeoShi$ cat .ssh/id_rsa.pub 
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDNbzDUT8uWQ/p1CY1hKbGuqIyn8e9OJe5asqP87rSk0NvI8x6WDwpMvHnj1OYcjw5TDSj6ioGq/LN+Isci2QVMR3Nh5FMy2GHqa2MRKh29iVXf1fBtXb1Nk8zCOLvK6U8Yr6S+DPEv8yKejRNOzlzNErSASE1WVMoWFfETVR1oZuq52xxra8EcVfAi22W2M6uc2knVT0iEMOTFxf+2iqn6pi8FxWegjn7z6rFGlYntlenpHwjRo11Xk2UAUv3ACcj84yp6lEb7HI2bcaLjksZneBBHcAZyTdxOebjJI+w8lqPrmmpkxKLTj6pZEe9fM6wv3DGJajWaQoMHn42F3jAn LeoShi@example.com
````

### END