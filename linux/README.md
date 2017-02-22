# Shortcuts for Linux

1. [MacOS Shortcuts](macos-shortcuts.md)
* [Linux Shortcuts](Linux_Shortcuts.md)
* [VI | VIM Shortcuts](vim.md)

------
##Linux Shortcuts
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
------
##Vim
###command shortcut
Command       |  Description
---|---
:set nu | show line number
:set nonu | hide line number
:6,9 co 12| 复制第6行到第9行之间的内容到第12行后面。 copy
:6,9 m 12 | 剪切第6行到第9行之间的内容到第12行后面。 move
:6(,9) de | 删除一行或多行
:m,n w {filename} | save lines m - n of this file to a new file {filename}
:{n} | jump to line n
:1,$s/keyword1/keyword2/g{c} | text replace，最后一个参数是询问参数

###Shortcut快捷键
Shortcut      |  Description
---|---
Shift + 4 | 行尾  $
Shift + 6 | 行首  ^
shift + g | go to last line of the file. 跳文件尾行
   g g    | go to first line of the file. 跳文件首行
   y y    | copy current line 拷贝行
   3 y y  | copy the current line after the 3 lines. 拷贝当前行起3行
   d d    | delete current line 删除行
   3 d d  | delete the current line after the 3 lines.删除当前行起3行
   p      | paste 粘贴
   10     | 向后跳 10行
   H      | 光标移动到屏幕最顶行
   M      | 光标移动到屏幕中间行
   G      | 光标移动到屏幕最尾行

###翻屏
Shortcut      |  Description
---|---
ctrl + f      | 下翻一屏。
ctrl + b      |  上翻一屏。
ctrl + d      | 下翻半屏。
ctrl + u      |  上翻半屏。
ctrl + e      |  向下滚动一行。
ctrl + y      |  向上滚动一行。
n%            | 到文件n%的位置。
zz            |  将当前行移动到屏幕中央。
zt            | 将当前行移动到屏幕顶端。
zb            | 将当前行移动到屏幕底端。

