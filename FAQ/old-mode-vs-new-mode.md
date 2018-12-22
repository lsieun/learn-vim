# git diff提示filemode发生改变

URL: [git diff提示filemode发生改变](https://www.cnblogs.com/sunzhenxing19860608/p/6066394.html)

今天clone代码，git status显示修改了大量文件，git diff提示filemode变化，如下：

```bash
diff --git a/Android.mk b/Android.mk
old mode 100644
new mode 100755
```

原来是filemode的变化，文件chmod后其文件某些位是改变了的，如果严格的比较原文件和chmod后的文件，两者是有区别的，但是源代码通常只关心文本内容，因此chmod产生的变化应该忽略，所以设置一下：

切到源码的根目录下，

```bash
git config --add core.filemode false
```

这样你的所有的git库都会忽略filemode变更了～

