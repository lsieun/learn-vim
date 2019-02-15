# Tricks

## Turn On Relative Line Numbers

```vim
:set relativenumber
```

`:set rnu` to turn on relative numbers and `:set nornu` to turn off the same.

## Know the path of the file you are editing

```vim
:pwd
```

## Open source of any URL

```bash
vim 'https://codingdash.com/'
```

## 缩进

```vim
> （当前行）缩进
>2j 将当前行及下面两行进行缩进
```

## Change+查找

```vim
c/other    # 一直change到"other"单词
```

## f

```
fx     #在这一行中，快带找到下一个x
```

## 切换大小写

```
~   #切换当前字符大小写
5~  #切换5个字符的大小写
```

## 显示相对行号

```vim
:set relativenumber
6dd 删除6行
:set norelativenumber
```

## 将raw headers转换成Python的dict

```
:%s/\(.*\):[[:blank:]]\+\(.*\)/    "\1": "\2"/g
:%s/\(.\{-}\):\s\+\(.*\)/    "\1": "\2"/g
```

`\{-}` 表示前一个字符可出现零次或多次（这一点与`*`相同），但在整个正则表达式可以匹配成功的前提下，匹配的字符数越少越好（这一点表示非贪婪模式）。

https://www.youtube.com/watch?v=wlR5gYd6um0



普通模式
pdi[ 删除一对 [] 中的所有字符
di( 删除一对 () 中的所有字符
di< 删除一对 <> 中的所有字符
di{ 删除一对 {} 中的所有字符
dit 删除一对 HTML/XML 的标签内部的所有字符
di” di’ 删除一对引号字符 (” 或 ‘ 中所有字符
插入模式
ci[ 删除一对 [] 中的所有字符并进入插入模式
ci( 删除一对 () 中的所有字符并进入插入模式
ci< 删除一对 <> 中的所有字符并进入插入模式
ci{ 删除一对 {} 中的所有字符并进入插入模式
cit 删除一对 HTML/XML 的标签内部的所有字符并进入插入模式
ci” ci’ 删除一对引号字符 (” 或 ‘ 中所有字符并进入插入模式
选择模式
vi[ 选择一对 [] 中的所有字符
vi( 选择一对 () 中的所有字符
vi< 选择一对 <> 中的所有字符
vi{ 选择一对 {} 中的所有字符
vit 选择一对 HTML/XML 的标签内部的所有字符
vi” vi’ 选择一对引号字符 (” 或 ‘中所有字符


在命令模式下启动进入纵向编辑模式
在windows下是用ctrl+q
在linux下是用ctrl+v
注意：这时在状态栏底下就会出现 ”-- 可视块 --“，代表可以操作块了

批量修改某一列的数据，假设有如下的数据
192.168.0.10
192.168.0.11
192.168.0.12
比如把192改为193，操作如下：
把光标移动到最顶部 192 的 2 上
在 linux 下按 ctrl+q
进入块编辑模式，按下 j
选择需要修改的 2
按下 r, 输入 3
说明：这种方法也可以用正则表达式来替代，操作如下： 1,3s/<192>/193/gc 就可以，效果如下：









