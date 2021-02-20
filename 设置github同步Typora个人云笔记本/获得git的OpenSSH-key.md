# 获得git的OpenSSH Key (Win版)

###### ### 个人学习整理，仅供参考

+ ####  [安装github](.\安装git软件.md)


### 指令获取OpenSSH Key

+ 启动Git Bash

+ 执行 

  ```
  $ cd ~/.ssh
  ```

  若返回语句为

  ```
  bash: cd: /c/Users/20678/.ssh: No such file or directory
  ```

  说明没有生成过SSH Key

  若曾生成过，则备份原生成密钥

  ```
  $ mkdir key_backup mv id_isa*key_backup
  ```

+ 生成新Key

  ```
  $ ssh-keygen -t rsa -C "<你的邮箱>"
  ```

  ```
  Generating public/private rsa key pair.
  Enter file in which to save the key (/c/Users/20678/.ssh/id_rsa):
  ```

  Tip: 不建议修改密钥保存地址，没有必要，徒增烦恼。

  ```
  $ Enter passphrase (empty for no passphrase):
  ```

  Tip: 设置密码，每次使用密钥登录时，需要输入；或者直接回车;

  ```
  Your identification has been saved in /c/Users/20678/.ssh/id_rsa
  Your public key has been saved in /c/Users/20678/.ssh/id_rsa.pub
  The key fingerprint is:
  SHA256:muPf+422+F5X/UDu1wJQjh/yO+zp7ncqw0QjldSPR/w 18556138746@163.com
  The key's randomart image is:
  +---[RSA 3072]----+
  |           .oo . |
  |           +o . o|
  |          +.o .+.|
  |          .=o+. E|
  |        S  o+.o.o|
  |       o   ..+ .+|
  |      +    o+ + =|
  |     . . . o=*.+.|
  |      ... +X%=oo |
  +----[SHA256]-----+
  ```

  此时，密钥生成成功

### 复制密钥

+ 指令

  ```
  $ clip < ~/.ssh/id_rsa.pub
  ```

  至此，密钥复制结束