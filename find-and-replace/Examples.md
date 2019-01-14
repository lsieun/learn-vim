# Examples

In the examples that follow, a square (`□`) is used to mark a **space**; it is not a special character.

删除空白行

- `:g/^$/d`: Delete all blank lines
- `:g/^[□tab]*$/d`: Delete all blank lines, plus any lines that contain only whitespace

将多个空格转换为一个空格

- `:%s/□□*/□/g`: Replace one or more spaces with a single space
- `:%s/:□□*/:□□/g`: Replace one or more spaces following a colon with two spaces
- `:%s/\([:.]\)□□*/\1□□/g`: Replace one or more spaces following a period or a colon with two spaces

删除开始或结尾多余的空格

- `:%s/^□□*\(.*\)/\1/`: Delete all leading spaces on every line
- `:%s/\(.*\)□□*$/\1/`: Delete all spaces at the end of every line

在开始和结尾添加空格

- `:%s/^/>□□/`: Insert a ">□□" at the start of every line in a file
- `:.,+5s/$/./`: Add a period to the end of the next six lines

大写转换

- `:%s/.*/\U&/`: Change every letter in a file to uppercase
- `:%s/./\U&/g`: 同上

行号逆序

- `:g/.*/mo0`: Reverse the order of lines in a file
- `:g/^/mo0`: 同上

