# iterm2-zmodem
苹果MAC下，用item2做上传和下载操作，完成lrzsz功能。

# 步骤

1.安装支持rz和sz命令的lrzsz：`brew install lrzsz`


2.在本地/usr/local/bin/目录下保存iterm2-send-zmodem.sh 和iterm2-recv-zmodem.sh两个脚本
（如图1）

3.设置一下两个脚本的权限，一般 chmod 777 就行了


chmod 777 /usr/local/bin/iterm2-*



4.设置Iterm2，profiles->default->editProfiles->Advanced中的Tirgger

添加两条trigger，分别设置 Regular expression，Action，Parameters，Instant如下：


1.第一条
        Regular expression: rz waiting to receive.\*\*B0100
        Action: Run Silent Coprocess
        Parameters: /usr/local/bin/iterm2-send-zmodem.sh
        Instant: checked
2.第二条
        Regular expression: \*\*B00000000000000
        Action: Run Silent Coprocess
        Parameters: /usr/local/bin/iterm2-recv-zmodem.sh
        Instant: checked