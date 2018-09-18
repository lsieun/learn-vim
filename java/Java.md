# Java

- code completion
- debuging tools
- compile and build of the project
- resource management
- project tree

https://github.com/vrapper/vrapper

https://medium.com/@Sohjiro/setup-vim-checkstyle-java-d0dd74dca1e1

The way that I replaced that tool, was with Vim. But, not Vim alone. Programming with only pure and plain Vim should be considered as a suicidal act. Why do I say that? Because, Vim is a highly configurable text editor built to make creating and changing any kind of text very efficient. By default, Vim has support for autocompletion (not the one that I mentioned before), supports syntax highlighting, supports hundreds of programming languages and file formats, among other things. That’s why I’m using Vim with a couple of plugins to make my life easier.

https://blog.lazyhacker.com/2012/02/vundle-to-manage-my-vim-plugins.html

That lead me to Eclim which is an Eclipse and VIM plugin combo that allowed VIM to access Eclipse's functionality.  This is pretty cool as it allowed me to do most of my work in VIM and switch to Eclipse when I needed to.  While this solution works, I started getting the itch to see how VIM can handle some of the tasks I was depending on Eclipse for so I started looking at various VIM plugins which led me to research how to manage plug-ins in general.

URL: https://stackoverflow.com/questions/253170/tips-for-using-vim-as-a-java-ide

http://shawnleezx.github.io/blog/2013/10/03/note-code-java-under-vim/

https://www.techrepublic.com/article/configure-vi-for-java-application-development/

http://sparkgis.com/2018/06/29/eclipse-4-8-photon-%E6%AD%A3%E5%BC%8F%E7%89%88%E5%8F%91%E5%B8%83%EF%BC%81%E5%AE%8C%E5%85%A8%E6%94%AF%E6%8C%81-java-10-%E5%BC%80%E6%BA%90%E4%B8%AD%E5%9B%BD%E7%A4%BE%E5%8C%BA/


- Make sure you use vim (vi improved). 
- You can get code completion with [eclim](http://eclim.org/)
- Syntax highlighting is great with vim
- Vim has good support for writing little macros like running ant/maven builds

## eclim

URL: http://eclim.org/

### What

如何认识Eclim：

- （1）Vim是一个文本编辑器
- （2）Eclim是Vim编辑器的一个插件
- （3）Eclim能够提供Eclipse的功能。例如，code completion, searching, code validation

### How do I get/install it?

URL: http://eclim.org/install.html


```txt
The eclim install completed successfully.
You can now start the eclimd server by executing the script:
  /home/liusen/Software/eclipse_photon/eclipse/eclimd

For more information please see the eclimd server documentation:
  http://eclim.org/eclimd.html
For information on using eclim, please visit the getting started guide:
  http://eclim.org/gettingstarted.html

```

http://eclim.org/eclimd.html
http://eclim.org/vim/code_completion.html

```vim
:ShutdownEclim
```

```vim
Plugin 'file:///home/liusen/.vim/bundle/eclim/eclim'
```

## Getting Started

URL: http://eclim.org/gettingstarted.html


## Maven Users

URL: http://eclim.org/gettingstarted.html#maven-users


## Other

http://eclim.org/vim/java/index.html

http://eclim.org/vim/java/classpath.html

http://eclim.org/vim/core/project.html#projectcreate


