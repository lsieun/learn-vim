# filetype

```vim
:help filetype
```

1. Filetypes
2. Filetype plugin
3. Docs for the default filetype plugins.

[TOC]

## 1. Filetypes

Vim can detect the type of file that is edited.  This is done by checking **the file name** and sometimes by inspecting **the contents of the file** for specific text.

> 检查filetype的两种方法：filename 和 file content。

To **enable file type detection**, use this command in your vimrc:

```vim
:filetype on
```

Each time a new or existing file is edited, Vim will try to recognize the type of the file and set the '`filetype`' option.  This will trigger the `FileType` event, which can be used to set the syntax highlighting, set options, etc.

If the file type is not detected automatically, or it finds the wrong type, **you can either set the `filetype` option manually**, or add a modeline to your file.  Example, for an `IDL` file use the command:

```vim
:set filetype=idl
```

To see the current status, type: 

```vim
:filetype
```

The output looks something like this:

```txt
filetype detection:ON  plugin:ON  indent:OFF
```


> 上面是讲 `filetype`  
> 下面开始讲 `filetype plugin`

You can **enable loading the plugin files for specific file types** with:

```vim
:filetype plugin on
```

If **filetype detection** was not switched on yet, it will be as well.
This actually loads the file "`ftplugin.vim`" in '`runtimepath`'.
**The result** is that when a file is edited **its plugin file is loaded** (if there
is one for the detected filetype). |filetype-plugin|

> 上面是讲 `filetype plugin`  
> 下面开始讲 `filetype indent`

You can enable loading the indent file for specific file types with:

```vim
:filetype indent on
```
If **filetype detection** was not switched on yet, it will be as well.
This actually loads the file "`indent.vim`" in '`runtimepath`'.
**The result** is that when a file is edited **its indent file is loaded** (if there is one for the detected filetype). 

