#Linux Shortcuts(Terminal)

[List of Unix commands](https://en.wikipedia.org/wiki/List_of_Unix_commands)

[wikipedia-find](https://en.wikipedia.org/wiki/Find)

Shortcut| Desciption
---|---
Ctrl - a| 行首
Ctrl - e| 行尾
Ctrl - w| 删除前一段参数
Ctrl - u| 删除光标位字符至行首（常用密码输错）
Ctrl - k| 删除光标位字符至行尾
Ctrl - r| history中搜索命令去执行
Ctrl - y| 插入刚删除的单词
Ctrl - c| 终止操作
Ctrl - d| logout
Ctrl - l （command-k）| 清屏

##grep
Linux 查找包含指定字符串的所有文件，及所在行
grep -rn "hello,world!" *
```text
* : 表示当前目录所有文件，也可以是某个文件名

-r 是递归查找
-n 是显示行号
-R 查找所有文件包含子目录
-i 忽略大小写

下面是一些有意思的命令行参数：
grep -i pattern files ：不区分大小写地搜索。默认情况区分大小写， 
grep -l pattern files ：只列出匹配的文件名， 
grep -L pattern files ：列出不匹配的文件名， 
grep -w pattern files ：只匹配整个单词，而不是字符串的一部分（如匹配‘magic’，而不是‘magical’）， 
grep -C number pattern files ：匹配的上下文分别显示[number]行， 
grep pattern1 | pattern2 files ：显示匹配 pattern1 或 pattern2 的行， 
grep pattern1 files | grep pattern2 ：显示既匹配 pattern1 又匹配 pattern2 的行。 
这里还有些用于搜索的特殊符号：

\< 和 \> 分别标注单词的开始与结尾。

例如： 
grep man * 会匹配 ‘Batman’、‘manic’、‘man’等， 
grep '\<man' * 匹配‘manic’和‘man’，但不是‘Batman’， 
grep '\<man\>' 只匹配‘man’，而不是‘Batman’或‘manic’等其他的字符串。 
'^'：指匹配的字符串在行首， 
'$'：指匹配的字符串在行尾

2，xargs配合grep查找
find -type f -name '*.php'|xargs grep 'GroupRecord'
```

##find
find 目录中搜索文件
```text
查找指定时间内修改过的文件:  
1. 48小时内修改过的文件 > find -atime -2
2. 关键字查找 > find . -name "*.log"
3. 目录按权限查文件 > find . -perm 777
4. 目录按类型查找 > find . -type f name "*.log"
5. 目录查找并排序 > find . -type d | sort
6. 目录按大小查找 > find . -size +1000c -print    # c是字节，+大于， -小于
```
1．命令格式：
find pathname -options [-print -exec -ok ...]    

**-ok -exec 表示操作前要询问用户。**
**-print 将查找到的文件输出到标准输出**
**-exec    command    {} \;       -----将查到的文件执行command操作,{} 和 \;之间有空格
**
```text
1. 基本用法：
      find / -name 文件名      find ver1.d ver2.d -name '*.c' -print    查找ver1.d,ver2.d *.c文件并打印      find . -type d -print 从当前目录查找，仅查找目录，找到后，打印路径名。可用于打印目录结构。
2. 无错误查找：
      find / -name access_log 2 >/dev/null
3. 按尺寸查找：
      find / -size 1500c （查找1,500字节大小的文件，c表示字节）
      find / -size +1500c （查找大于1,500字节大小的文件，+表示大于）    
      find / -size +1500c （查找小于1,500字节大小的文件，-表示小于）    
4. 按时间：
      find / -amin n 最后n分钟 
      find / -atime n 最后n天
      find / -cmin n 最后n分钟改变状态
      find / -ctime n 最后n天改变状态
5. 其它：
      find / -empty 空白文件、空白文件夹、没有子目录的文件夹
      find / -false 查找系统中总是错误的文件
      find / -fstype type 找存在于指定文件系统的文件，如type为ext2
      find / -gid n 组id为n的文件
      find / -group gname 组名为gname的文件
      find / -depth n 在某层指定目录中优先查找文件内容
      find / -maxdepth levels 在某个层次目录中按递减方式查找
6. 逻辑
      -and 条件与 -or 条件或
7. 查找字符串
      find . -name '*.html' -exec grep 'mailto:'{}
```

