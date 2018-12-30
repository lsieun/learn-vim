# Learn VIM

学习使用VIM



## 使用方法

第一步，切换到用户的`home`目录，使用`git clone`命令克隆仓库

```bash
# 切换到用户的home目录
$ cd ~
# 克隆仓库
$ git clone https://github.com/lsieun/.vim
```

第二步，下载Vundle

```bash
# 创建文件夹
$ mkdir -p ~/.vim/bundle
# 克隆Vundle仓库
$ git clone https://github.com/gmarik/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

第三步，使用Vundle，更新Vundle插件

（1）打开vim

```bash
$ vim
```

（2）对Vundle插件进行更新，使用如下命令：

```bash
:PluginInstall
```

## 学习参考

URL: [Vim Tips Wiki](http://vim.wikia.com/wiki/Vim_Tips_Wiki)
