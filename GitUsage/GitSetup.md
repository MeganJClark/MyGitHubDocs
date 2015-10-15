# Setting up Git
The first time you use git, you will need to configure your user account and your default editor. All operating systems can do this in the terminal or power shell once Git is installed.

For user accounts, type the following in terminal or Power Shell

```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

To configure the default text editor type the following and replace "emacs" with your editor of choice. **Note** if this variable is not configured, Git will use your system's default editor.
```
$ git config --global core.editor emacs
```

If you'd like to check your settings, the following command will list all settings Git can find at that point:
```
$ git config --list
```

You can check a specific value by typing *git config "key"* like so:
```
$ git config user.name
John Doe
```

If you need more help, or want to explore other commands you can get to the manpage for the config command by typing:

```
$ git help config
```
