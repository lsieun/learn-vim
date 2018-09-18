# workspace

## How do I tell eclim which eclipse workspace to use?

URL: http://eclim.org/faq.html

To configure the workspace you can start `eclimd` like so:

```bash
$ eclimd -Dosgi.instance.area.default=@user.home/another_workspace
```

Note the system property `osgi.instance.area.default`, which is used to specify **the location of your workspace**. Also note the variable `@user.home` which will be replaced with **your home directory** at `runtime`.

If you are running a unix variant (linux, mac osx, bsd, etc.) then you can specify the above system property in the `.eclimrc` file in **your home directory**.

```bash
$ echo "osgi.instance.area.default=@user.home/another_workspace" >> ~/.eclimrc
```

