#Terminal

Terminal快捷键:

	CTRL SHIT T     打开新的Terminal
	CTRL D		关闭Terminal
	CTRL +		增加字体
	CTRL -          减小字体
		
#Bash

Bash快捷键:

	CTRL L		清空屏幕
	Tab		命令补全(详细看配置文档)
	CTAL A		跳转到行首
	CTRL D		删除字符
	CTRL E		跳转到行尾
	CTRL <- ->	不同单词间切换
	CTRL W		替换单词
	CTRL F/B	光标前后移动
	ALT  F/B	光标在单词间前后移动

#PATH环境变量

##添加环境变量
	1.零时添加环境变量(_关闭shell,还原PATH环境变量_)
	PATH=$PATH:user/bin
	2.修改profile文件(attention:重启生效)
	$vi /etc/profile 
	在里面加入:
	export PATH="$PATH:." 		
	3.修改.bashrc文件(attention:重启生效)
	$vi /root/.bashrc 
	在里面加入： 
	export PATH="$PATH:/my_new_path" 
##显示环境变量
	1.echo $PATH
