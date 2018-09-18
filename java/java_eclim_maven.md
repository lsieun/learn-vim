


# create maven project

URL: http://eclim.org/gettingstarted.html#maven-users

1、Run maven’s generate archetype to create the project directory and samples:

```bash
$ mvn archetype:generate
```

2、Once you’ve created the initial project directory, `cd` into that directory and run the following command to generate the necessary eclipse files:

```bash
$ cd <project_dir>
$ mvn eclipse:eclipse
```


It(`mvn eclipse:eclipse`) will update your repository with all the missing jars, according to your dependencies in your `pom.xml` file.

3、Now you can start an instance of vim at the project’s root directory and run the following commands to:

- set the necessary eclipse classpath variable to point to your maven repository.
- import your new project into eclipse.

```
$ vim
:MvnRepo
:ProjectImport /path/to/new/project
```

## Maven & classpath

URL: http://eclim.org/vim/java/classpath.html

Maven comes bundled with **an Eclipse plugin** that allows you to easily maintain your `.classpath` file based on your `pom.xml`.

> 这段的两个意思：  
> （1）Maven有一个maven-eclipse-plugin插件；  
> （2）这个插件的作用是将`pom.xml`中的jar维护到`.classpath`文件内。

- Initial Setup

To initialize maven’s support for updating the **eclipse classpath** you first need to set the `M2_REPO` classpath variable in **the Eclipse workspace** by executing the following command in vim:

```vim
:MvnRepo
```

- Updating your `.classpath`

Once you have performed the initial setup, updating the Eclipse `.classpath` file is as easy as executing the following at a command line:

```bash
mvn eclipse:eclipse
```

or in Vim:

```vim
:Mvn eclipse:eclipse
```

For maven 2.x users, eclim also provides support for **auto updating** the `.classpath` for your project every time you save your `pom.xml` file. Any entries found in the `pom.xml` that are not in the `.classpath` will be added, any entries that differ in version will be updated, and any stale entries deleted.

This behavior can be disabled by adding the following setting to your vimrc:

```vim
let g:EclimMavenPomClasspathUpdate = 0
```

This feature **simply** updates the entries in your project’s `.classpath` file, it **does not** download any newly added jars. When you’d like maven to download those new jars, you can run the following from the command line:

```bash
mvn dependency:resolve
```

or from within Vim:

```vim
:Mvn dependency:resolve
```

## Junit

According to the [JUnit GitHub team website](https://github.com/junit-team/junit/wiki/Download-and-Install), `junit.jar` and `hamcrest-core.jar` are both needed in the classpath when using JUnit 4.12.

Here is the Maven dependency block for including `junit` and `hamcrest`.

```xml
<dependency>
    <groupId>junit</groupId>
    <artifactId>junit</artifactId>
    <version>4.12</version>
    <scope>test</scope>
</dependency>
<!-- Needed by junit -->
<dependency>
    <groupId>org.hamcrest</groupId>
    <artifactId>hamcrest-all</artifactId>
    <version>1.3</version>
    <scope>test</scope>
</dependency>
```

## Running

Eclim provides the following commands:

```vim
:Maven [<goal> ...]
:Mvn [<goal> ...]
```

## mvn commands

```bash
mvn help:effective-pom  # to look at the default configurations of the super POM
```

```bash
mvn dependency:sources  # 能够把当前项目依赖的lib包的源码包从服务器上down下来，不错的命令啊
```

