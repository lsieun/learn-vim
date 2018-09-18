# Automated Imports

URL: http://eclim.org/vim/java/import.html

The automated import functionality is pretty straightforward. Simply place **the cursor** over **the element** to import and issue the command:

```vim
:JavaImport
```

and one of the following events will occur:

- If **only one matching element** is found, its import statement will be placed in the file.
- If **multiple matching elements** are found, you will be prompted to choose the element you wish to import from a list.
- If **an element with the same name is already imported**, the element is in java.lang, or the element is in the same package as the current src file, then no changes will occur.

In addition to adding imports **one by one**, you can also **add them in bulk** along with **the removal of unused imports** and **the sorting** and **formating** of all the file’s import statements using the command:

```vim
:JavaImportOrganize
```
