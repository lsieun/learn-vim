# emmet-vim

URL:

- https://github.com/mattn/emmet-vim/
- https://raw.githubusercontent.com/mattn/emmet-vim/master/TUTORIAL

[TOC]

## 1. Installation

To install using Vundle:

```vim
" add this line to your .vimrc file
Plugin 'mattn/emmet-vim'
```

## 2. Configuration

### 2.1 Enable in different mode

> 这一部分内容是设置在Insert/Normal/Visual模式下的有效性。

If you don't want to enable emmet in all modes, you can use set these options in vimrc:

```vim
let g:user_emmet_mode='n'    "only enable normal mode functions.
let g:user_emmet_mode='inv'  "enable all functions, which is equal to
let g:user_emmet_mode='a'    "enable all function in all mode.
```

### 2.2 Enable just for html/css

```vim
let g:user_emmet_install_global = 0
autocmd FileType html,css EmmetInstall
```

### 2.3 Redefine trigger key

To remap the default `<C-Y>` leader:

```vim
let g:user_emmet_leader_key='<C-Z>'
```

Note that the trailing "`,`" still needs to be entered, so the new keymap would be `<C-Z>,`.

### 2.4 Adding custom snippets

> 这一部分内容，我没有看懂，不知道web-api是做什么用的。

If you have installed the [web-api](https://github.com/mattn/webapi-vim) for **emmet-vim** you can also add your own snippets using a custom `snippets.json` file.

Once you have installed the **web-api** add this line to your `.vimrc`:

```vim
let g:user_emmet_settings = webapi#json#decode(join(readfile(expand('~/.snippets_custom.json')), "\n"))
```

You can change the **path** to your `snippets_custom.json` according to your preferences.

[Here](http://docs.emmet.io/customization/snippets/) you can find instructions about creating your customized `snippets.json` file.


## 3. Tutorial

### 3.1 html

Open or create a New File:

```bash
vim index.html
```

Type ("`_`" is the cursor position):

```txt
html:5_
```

Then type `<c-y>,`, and you should see:

```html
<!DOCTYPE HTML>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title></title>
</head>
<body>
	_
</body>
</html>
```

### 3.2 

URL:

- https://raw.githubusercontent.com/mattn/emmet-vim/master/TUTORIAL

- Type the abbreviation as '`div>p#foo$*3>a`' and type '`<c-y>,`'.
- Go to the Next Edit Point: type '`<c-y>n`' in insert mode.
- Go to the Previous Edit Point: type '`<c-y>N`' in insert mode.
- Remove a Tag: Move cursor in block, Type '`<c-y>k`' in insert mode.
- Toggle Comment: Type '`<c-y>/`' in insert mode.



