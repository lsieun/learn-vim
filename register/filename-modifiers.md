# filename-modifiers

```vim
:help filename-modifiers
```

## 1. 文件名修饰符

**The file name modifiers** can be used after "`%`", "`#`", "`#n`", "`<cfile>`", "`<sfile>`", "`<afile>`" or "`<abuf>`".

These modifiers can be given, in this order:


- `:p`	Make file name a full path.  Must be the first modifier.
- `:~`	Reduce file name to be relative to the home directory, if possible.
- `:.`	Reduce file name to be relative to current directory, if possible.
- `:h`	Head of the file name (the last component and any separators removed).  Cannot be used with `:e`, `:r` or `:t`.
- `:t`	Tail of the file name (last component of the name).  Must precede any `:r` or `:e`.
- `:r`	Root of the file name (the last extension removed). 
- `:e`	Extension of the file name.  Only makes sense when used alone.

> 这些分成3组来记忆：  
> （1）`:p`, `:.`, `:~` 分别对应了绝对路径、相对路径、相对用户路径  
> （2）`:h`和`:t`分别代表Head和Tail，它们的分隔应该是路径分隔符`/`分隔  
> （3）`:r`和`:e`分别代表Root和Extention，它们的分隔应该是`.`分隔


## 2. 示例

文件路径是：`/home/liusen/workdir/dummy/HelloWorld.java`  
当前目录是：`/home/liusen/workdir`

| modifier | vim ex command            | Output                                       |
| -------- | ------------------------- | -------------------------------------------- |
| DEFAULT  | `:echo expand("%")`       | `dummy/HelloWorld.java`                      |
| `:p`     | `:echo expand("%:p")`     | `/home/liusen/workdir/dummy/HelloWorld.java` |
| `:.`     | `:echo expand("%:.")`     | `dummy/HelloWorld.java`                      |
| `:~`     | `:echo expand("%:~")`     | `~/workdir/dummy/HelloWorld.java`            |
| `:h`     | `:echo expand("%:h")`     | `dummy`                                      |
| `:p:h`   | `:echo expand("%:p:h")`   | `/home/liusen/workdir/dummy`                 |
| `:p:h:h` | `:echo expand("%:p:h:h")` | `/home/liusen/workdir`                       |
| `:t`     | `:echo expand("%:t")`     | `HelloWorld.java`                            |
| `:p:t`   | `:echo expand("%:p:t")`   | `HelloWorld.java`                            |
| `:r`     | `:echo expand("%:r")`     | `dummy/HelloWorld`                           |
| `:p:r`   | `:echo expand("%:p:r")`   | `/home/liusen/workdir/dummy/HelloWorld`      |
| `:t:r`   | `:echo expand("%:t:r")`   | `HelloWorld`                                 |
| `:e`     | `:echo expand("%:e")`     | `java`                                       |
|          |                           |                                              |
|          |                           |                                              |


