
使用vim的一个难点在于：你不知道该怎么使用它，究其原因，是因为见到使用的场景太少了。

这个需要不断的练习。


keyword completion: Ctrl+P
Whole line completion: Ctrl+X Ctrl+L
File Name completion: Ctrl+X Ctrl+F

```
dt(    # 删除直到(
dt"    # 删除直到"
3fa → 在当前行查找第三个出现的a。
```

http://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/

`:history`也可以查看vim的命令历史

高手进阶：

i 表示 inside，打开 Vim 后，执行 `:help object-select` 可以看详细介绍。

verb(action): single character verb / 

第二种类型的verb，可以与motion和text object进行组合
motion: 可以单独使用
text object： 


https://pan.baidu.com/s/1o7fwx6H7Yec0JRbjnC9WmA 密码：ykxx


## 网站 ##

[Learning Vim in 2014: Vim as Language](https://benmccormick.org/2014/07/02/learning-vim-in-2014-vim-as-language/)

[How To Learn Vim: A Four Week Plan](https://medium.com/actualize-network/how-to-learn-vim-a-four-week-plan-cd8b376a9b85)

```
vimtutor
```

Vim中的正则表达式

. 匹配任意一个字符
[abc] 匹配方括号中的任意一个字符。可以使用-表示字符范围，如[a-z0-9]匹配小写字母和阿拉伯数字
[^abc] 在方括号内开头使用^符号，表示匹配除方括号中字符之外的任意字符
\d 匹配阿拉伯数字，等同于[0-9]
\D 匹配阿拉伯数字之外的任意字符，等同于[^0-9]
\x 匹配十六进制数字，等同于[0-9A-Fa-f]
\X 匹配十六进制数字，等同于[^0-9A-Fa-f]
\w 匹配单词字母，等同于[0-9A-Za-z_]
\W 匹配单词字母之外的任意字符，等同于[^0-9A-Za-z_]
\t 匹配<TAB>字符
\s 匹配空白字符，等同于[ \t]
\S 匹配非空白字符，等同于[^ \t]
\a 所有的字母字符. 等同于[a-zA-Z]
\l 小写字母 [a-z]
\L 非小写字母 [^a-z]
\u 大写字母 [A-Z]
\U 非大写字母 [^A-Z]

表示数量的元字符
* 匹配0-任意个
\+ 匹配1-任意个
\? 匹配0-1个
\{n,m} 匹配n-m个
\{n} 匹配n个
\{n,} 匹配n-任意个
\{,m} 匹配0-m个
\_. 匹配包含换行在内的所有字符
\{-} 表示前一个字符可出现零次或多次，但在整个正则表达式可以匹配成功的前提下，匹配的字符数越少越好
\= 匹配一个可有可无的项
\_s 匹配空格或断行
\_[]
\* 匹配 * 字符
\. 匹配 . 字符
\/ 匹配 / 字符
\\ 匹配 \ 字符
\[ 匹配 [ 字符

表示位置的符号
$ 匹配行尾
^ 匹配行首
\< 匹配单词词首
\> 匹配单词词尾

替换变量
在正规表达式中使用 和 符号括起正规表达式，即可在后面使用\1、\2等变量来访问 和 中的内容

懒惰模式
\{-n,m} 与\{n,m}一样，尽可能少次数地重复
\{-} 匹配它前面的项一次或0次, 尽可能地少
\| "或"操作符
\& 并列




