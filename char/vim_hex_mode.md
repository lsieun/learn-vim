# 如何在vim 中看到16进制的显示

view hex mode in vim
```vim
:%!xxd
```

return to normal mode from hex mode
```vim
:%!xxd -r
```

如果想了解关于xxd程序的更多用法，可在shell命令行下输入`man xxd`.

# Using Vim to Display a File in Hex

URL: https://medium.com/@tzhenghao/using-vim-to-display-a-file-in-hex-24996c9733c1

There are many ways to open/view a file in a hexadecimal representation. One way I can think of right now is to:

- Run `hexdump -C <filename> > output.txt` to open the file and save it onto a file called `output.txt`. You can then open this `output.txt` file separately and view it.
- Open the file in Vim directly as hexadecimal.


Let’s say you want option 2 cause it’ll save you some time (and not create a separate file). To do this, let’s create `simple .txt` file called `hello_world.txt` that contains “`Hello World!`”:

```bash
$ cat hello_world.txt
Hello World!
$ hexdump -C hello_world.txt
00000000 48 65 6c 6c 6f 20 57 6f 72 6c 64 21 0a |Hello World!.|
0000000d
```

Vim has a pretty cool feature that allows you to run **external shell command** without ever exiting it. Now if you open the file in Vim and type `:%!hexdump -C`