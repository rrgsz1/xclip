# xclip
剪切板与终端的通道

1 xclip
xclip命令建立了终端和剪切板之间通道，可以用命令的方式将终端输出或文件的内容保存到剪切板中，也可以将剪切板的内容输出到终端或文件
不加选项时只在保存在X PRIMARY（应该是终端剪切板），加上选项 -selection c后保存在 X CLIPBOARD（应该是外部程序剪切板）。
参考：http://www.debian-administration.org/articles/565
安装 sudo apt-get xclip

2 终端输出保存到剪切板中
ls -al | xclip
此时ls -al的输出内容已经保存在剪切板中了，此时xclip -o可以看到剪切板的内容。
但此时还不可以粘贴到终端以外的程序中，此时需要用到： xclip -selection c 
ls -al | xclip -selection c

3 文件内容复制到剪切板中
xclip /etc/apt/sources.list
xclip -selection c /etc/apt/sources.list

4 剪切板内容输出到终端
xclip -o
xclip -selection c -o

5 剪切板内容输出到文件
xclip -o > ~/test.txt
xclip -selection c -o > ~/test.txt
