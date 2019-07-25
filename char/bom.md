# UTF-8 with BOM is not recommended

- Tags: BOM

According to the Unicode standard, the BOM for UTF-8 files is not recommended.

While Unicode standard allows BOM in UTF-8, it does not require or recommend it. Byte order has no meaning in UTF-8 so a BOM only serves to identify a text stream or file as UTF-8 or that it was converted from another format that has a BOM.

- Open file in VIM:

```vim
vi text.xml
```

- Remove BOM encoding:

```vim
:set nobomb
```

- Save and quit:

```vim
:wq
```
