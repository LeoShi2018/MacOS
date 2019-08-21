### Macos brew 安装与使用

#### 安装

- 准备

````
MacBook-Pro:~ LeoShi$ ruby --version
-----ruby是安装的前提条件-------------------------
ruby 2.3.7p456 (2018-03-28 revision 63024) [universal.x86_64-darwin18]
````

- 安装

> 参考网站：https://brew.sh/index_zh-cn

````
MacBook-Pro:~ LeoShi$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
------------------------------
==> This script will install:
/usr/local/bin/brew
/usr/local/share/doc/homebrew
/usr/local/share/man/man1/brew.1
/usr/local/share/zsh/site-functions/_brew
/usr/local/etc/bash_completion.d/brew
/usr/local/Homebrew
==> The following existing directories will be made group writable:
/usr/local/sbin
==> The following existing directories will have their owner set to LeoShi:
/usr/local/sbin
==> The following existing directories will have their group set to admin:
/usr/local/sbin
==> The following new directories will be created:
/usr/local/bin
/usr/local/etc
/usr/local/include
/usr/local/lib
/usr/local/share
/usr/local/var
/usr/local/opt
/usr/local/share/zsh
/usr/local/share/zsh/site-functions
/usr/local/var/homebrew
/usr/local/var/homebrew/linked
/usr/local/Cellar
/usr/local/Caskroom
/usr/local/Homebrew
/usr/local/Frameworks

Press RETURN to continue or any other key to abort
-----回车-------------------------
==> /usr/bin/sudo /bin/chmod u+rwx /usr/local/sbin
Password: #输入Mackbook的密码
==> /usr/bin/sudo /bin/chmod g+rwx /usr/local/sbin
==> /usr/bin/sudo /usr/sbin/chown LeoShi /usr/local/sbin
......
HEAD is now at 84c5f4079 Merge pull request #6385 from EricFromCanada/man-page-text
==> Homebrew is run entirely by unpaid volunteers. Please consider donating:
  https://github.com/Homebrew/brew#donations
==> Tapping homebrew/core
Cloning into '/usr/local/Homebrew/Library/Taps/homebrew/homebrew-core'...
fatal: unable to access 'https://github.com/Homebrew/homebrew-core/': Failed to connect to github.com port 443: Operation timed out
Error: Failure while executing; `git clone https://github.com/Homebrew/homebrew-core /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core --depth=1` exited with 128.
Error: Failure while executing; `/usr/local/bin/brew tap homebrew/core` exited with 1.
Failed during: /usr/local/bin/brew update --force
# 错误提示略过
````
- 验证
````
MacBook-Pro:~ LeoShi$ which brew
-----如下提示安装成功-------------------------
/usr/local/bin/brew
````

#### 更换国内源

>参考：http://mirrors.ustc.edu.cn/help/brew.git.html

````
MacBook-Pro:local LeoShi$ cd "$(brew --repo)"
MacBook-Pro:Homebrew LeoShi$ git remote set-url origin https://mirrors.ustc.edu.cn/brew.git
MacBook-Pro:Homebrew LeoShi$ brew update
-----时间应该很快-------------------------
Already up-to-date.
````

- core
````
MacBook-Pro:Homebrew LeoShi$ mkdir -p /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core
MacBook-Pro:Homebrew LeoShi$ cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"         
MacBook-Pro:homebrew-core LeoShi$ git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-core.git
````
- cask

````
MacBook-Pro:~ LeoShi$ mkdir -p /usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask 
MacBook-Pro:~ LeoShi$ cd "$(brew --repo)"/Library/Taps/homebrew/homebrew-cask         
MacBook-Pro:homebrew-cask LeoShi$ git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-cask.git
````

#### 查找需要安装的软件包
````
MacBook-Pro:~ LeoShi$ brew search redis 
==> Casks
homebrew/cask/redis
````


### END