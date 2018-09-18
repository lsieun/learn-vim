# Java Search

URL: http://eclim.org/vim/java/search.html

在Vim当中，可以输入以下命令：

```vim
:help JavaSearch
```

## Pattern Search

Pattern searching provides a means to widen a search beyond a single element. A pattern search can be executed using the command

```vim
:JavaSearch -p <pattern> [-t <type> -x <context> -s <scope> -i -a <action>]
```

- `-p <pattern>`: The pattern to search for.

Ex.

```
MyClass*
MyClass.someMethod*
```

- `-t <type>` (Default: `type`): The type of element to search for where possible types include

    - `class`
    - `classOrEnum`
    - `classOrInterface`
    - `constructor`
    - `enum`
    - `field`
    - `interface`
    - `method`
    - `package`
    - `type`
    - `annotation`

- `-x <context>` (Default: `declarations`): The context of the search, where possible context values include

    - `all` - All occurrences.
    - `declarations` - Declarations matching the pattern or element.
    - `implementors` - Implementors of the pattern or element.
    - `references` - References of the pattern or element.

- `s <scope>` (Default: `all`): The scope of the search where possible values include

    - `all` - Search the whole workspace.
    - `project` - Search the current project, dependent projects, and libraries.

- `-i`: Ignore case when searching.

- `-a`: The vim command to use to open the result (`edit`, `split`, `vsplit`, `etc`).

Eclim also provides **a shortcut** when issuing a **pattern search** for a type. You may simply invoke `:JavaSearch` supplying **only** **the pattern**.

> 使用`:JavaSearch`的pattern search时，可以省略参数`-p`，只添加pattern参数。

```vim
:JavaSearch SomeType
```

To shorten things even more, there is support for **camel case searching** as well.

> 这里是首字母搜索camel case searching

```vim
:JavaSearch NPE
```

However, please note that **camel case searching** does not permit wild card characters (‘`*`’, ‘`?`’).

> **首字母搜索**并不支持`*`和`?`；  
> 言外之意，平常的查询支持`*`和`?`

## Element Search

```vim
:JavaSearchContext
```

This command accepts only the optional `-a` argument to open the result (`edit`, `split`, `vsplit`, etc), and will perform the appropriate search depending on the context of **the element** under **the cursor**.





