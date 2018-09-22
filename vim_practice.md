# vim practice

## Global Replacement

### 001

修改前：

```txt
    6、Don't  put off     till tomorrow   what should be done today. 今日事，今日畢。    

5、Where    there is a  will, there is   a way. 有志者事竟成。   
       
                  4、Failure    is the mother   of     success. 失敗是成功之母。  

          3、Time    will    tell. 時間會證明一切。    
                  
    2、All   roads lead   to Rome. 條條大路通羅馬。   

   1、It is   never too old to    learn. 活到老，學到老。    
```

修改后：

```txt
# 1、It is never too old to learn. 活到老，學到老。
# 2、All roads lead to Rome. 條條大路通羅馬。
# 3、Time will tell. 時間會證明一切。
# 4、Failure is the mother of success. 失敗是成功之母。
# 5、Where there is a will, there is a way. 有志者事竟成。
# 6、Don't put off till tomorrow what should be done today. 今日事，今日畢。
```

操作步骤如下：

> 注意：其中`□`表示“空格”。


- 删除没有任何字符的空白行：`:g/^$/d`
- 删除只有空格或tab键的行：`:g/^\s*$/d`
- 删除每行前面的空格：`:%s/^□*\(.*\)/\1/g` (`:%s/^ *\(.*\)/\1/g`)
- 在每行的前面加上`#□`：`:%s/^/#□/g` (`:%s/^/# /g`)
- 删除每行“`.`”之后的字符（即，删除中文翻译）：`:%s/\(.*\)\..*/\1./g`
- 取消上一次操作，删除每行末尾的空格（非贪婪模式）： 
    - `:s/\(.*\) */\1/g`
    - `:%s/\(.\{-}\)\s*$/\1/g`：正确
    - `:%s/\(.\{-}\)\s*/\1/g`：缺少一个`$`

- 将多个空格转换为一个空格：`:%s/□□*/□/g` (`:%s/  */ /g`)
- 文件内容顺序倒转：`:g/.*/m0`



处理的场景：

- 空白行
    - 没有任何空白字符
    - 有空格和Tab键的空白行
- 非空白行
    - 开头
    - 结尾
    - 中间

### 002

在保留空白行的情况下，删除每行中多余空格，并完成文档内容逆序：

- 选择非空白行：`:v/^\s*$/`
- 删除每行中的多余空格：`:s/□□*/□/g`
- 文档内容逆序：`:g/.*/m0`

第一次尝试：先删除非空白行中的多余空格，再进行文档内容逆序。

```vim
:v/^\s*$/s/  */ /g | :g/.*/m0
```

第二次尝试：先进行文档内容逆序，再删除非空白行中的多余空格。

```vim
:g/.*/m0 | :v/^\s*$/s/  */ /g
```

### 003

修改前：

```txt
# 1、It is never too old to learn. 活到老，學到老。




# 2、All roads lead to Rome. 條條大路通羅馬。


# 3、Time will tell. 時間會證明一切


# 4、Failure is the mother of success. 失敗是成功之母。




# 5、Where there is a will, there is a way. 有志者事竟成。



# 6、Don't put off till tomorrow what should be done today. 今日事，今日畢。
```

修改后：

```txt
# 1、It is never too old to learn. 活到老，學到老。

# 2、All roads lead to Rome. 條條大路通羅馬。

# 3、Time will tell. 時間會證明一切

# 4、Failure is the mother of success. 失敗是成功之母。

# 5、Where there is a will, there is a way. 有志者事竟成。

# 6、Don't put off till tomorrow what should be done today. 今日事，今日畢。
```

替换命令如下：

```vim
:%s/\(.*\)\n\{2,}/\1^M^M/g
```

将两个空格替换为1个空格的情况：将PDF中文件拷贝到文本文件中时，经常出现多个空格的情况。



```txt
1、Don't put off till tomorrow what should be done today. 今日事，今日畢。

2、Where there is a will, there is a way. 有志者事竟成。

3、Failure is the mother of success. 失敗是成功之母。

4、Time will tell. 時間會證明一切

5、All roads lead to Rome. 條條大路通羅馬。

6、It is never too old to learn. 活到老，學到老。

7、It is hard to fail, but it is worse never to have tried to succeed. – Theodore Roosevelt
```




