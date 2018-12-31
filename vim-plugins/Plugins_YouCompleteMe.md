# YouCompleteMe

Github: https://github.com/Valloric/YouCompleteMe

## Installation

```vim
Plugin 'Valloric/YouCompleteMe'
```

## Installation

These instructions (using `install.py`) are the quickest way to install **YouCompleteMe**.

> 安装YouCompleteMe最简单的方法是使用`install.py`。

Make sure you have **Vim 7.4.1578** with **Python 2** or **Python 3** support.

> 对于VIM和Python版本的要求。

The Vim package on Fedora 27 and later and the pre-installed Vim on Ubuntu 16.04 and later are recent enough. You can see the version of Vim installed by running `vim --version`. If the version is too old, you may need to compile Vim from source (don't worry, it's easy).

> 关于VIM的版本

Install YouCompleteMe with [Vundle](https://github.com/VundleVim/Vundle.vim#about).

Remember: YCM is a plugin with a compiled component. If you update YCM using Vundle and the ycm_core library APIs have changed (happens rarely), YCM will notify you to recompile it. You should then rerun the install process.

Install **development tools**, **CMake**, and **Python headers**:

**Fedora 27 and later**:

```bash
sudo dnf install cmake gcc-c++ make python3-devel
```

**Ubuntu 14.04**:

```bash
sudo apt install build-essential cmake3 python3-dev
```

**Ubuntu 16.04 and later**:

```bash
sudo apt install build-essential cmake python3-dev
```

Compiling YCM **with** semantic support for C-family languages:

```bash
cd ~/.vim/bundle/YouCompleteMe
python3 install.py --clang-completer
```

Compiling YCM **without** semantic support for C-family languages:

```bash
cd ~/.vim/bundle/YouCompleteMe
python3 install.py
```

The following additional language support options are available:

- **C# support**: install Mono and add `--cs-completer` when calling `install.py`.
- **Go support**: install Go and add `--go-completer` when calling `install.py`.
- **JavaScript and TypeScript support**: install Node.js and npm and add `--ts-completer` when calling `install.py`.
- **Rust support**: install Rust and add `--rust-completer` when calling `install.py`.
- **Java support**: install JDK8 (version 8 required) and add `--java-completer` when calling `install.py`.

To simply compile with everything enabled, there's a `--all` flag. So, to install with all language features, ensure xbuild, go, tsserver, node, npm, rustc, and cargo tools are installed and in your PATH, then simply run:

```bash
cd ~/.vim/bundle/YouCompleteMe
python3 install.py --all
```

## Config

```vim
let g:SimpylFold_docstring_preview=1
let g:ycm_autoclose_preview_window_after_completion=1
map <leader>g  :YcmCompleter GoToDefinitionElseDeclaration<CR>
```

### GoToDefinitionElseDeclaration

问题：如何返回呢？

使用`Ctrl+O`(后退)和`Ctrl+I`(前进)


使用命令`:YcmDiags`可以打开location-list查看警告和错误信息。






