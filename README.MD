link: https://rocket.chat/docs/installation/docker-containers/docker-compose

在执行的过程中要注意执行顺序

docker-compose up -d mongo

然后再去执行  docker-compose up rocketchat

运行起来以后注册的第一个账号默认就是超级管理员， 首先需要添加对中文房间名的支持：

Administration - General under UTF8 section  此处的值修改为： [^\x00-\x7F]+ 不允许使用英文，数字等 或者粗犷一点 .+ 什么字符都支持

修改系统的默认语言为中文

这个过程 rocketchat会重启， 重新启动 docker-compose up rocketchat

没问题后 ctrl z 把rocketchat 整到后台运行。

添加机器人账号： 
    - ROCKETCHAT_USER=bot
    - ROCKETCHAT_PASSWORD=botpassword