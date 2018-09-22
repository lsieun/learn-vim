# Vim indent xml file

URL: https://stackoverflow.com/questions/21408222/vim-indent-xml-file

First, highlight the XML you want to format.

Then, in normal mode, type `! xmllint --format -`

Your command-line at the bottom will look like this:

```vim
:'<,'>!xmllint --format -
```

Then hit `Enter`.

## Technical Explanation

The selected text is sent to the `xmllint`(command line XML tool) command, then `--format`'ed, and the results of `xmllint` are placed over **your selected text** in vim. The `-` at the end of the command is for **receiving standard input** - which, in this case, is the selected text that vim sends to xmllint.


http://vim.wikia.com/wiki/Pretty-formatting_XML