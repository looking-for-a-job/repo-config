<!--
https://readme42.com
-->



[![](https://img.shields.io/badge/OS-Unix-blue.svg?longCache=True)]()
[![](https://img.shields.io/pypi/v/repo-config.svg?maxAge=3600)](https://pypi.org/project/repo-config/)
[![](https://img.shields.io/npm/v/repo-config.svg?maxAge=3600)](https://www.npmjs.com/package/repo-config)[![](https://img.shields.io/badge/License-Unlicense-blue.svg?longCache=True)](https://unlicense.org/)
[![](https://github.com/andrewp-as-is/repo-config/workflows/tests42/badge.svg)](https://github.com/andrewp-as-is/repo-config/actions)

### Installation
```bash
$ [sudo] pip install repo-config
```

```bash
$ [sudo] npm i -g repo-config
```

#### How it works
`path/to/repo/.config/` - repo config

git@host:**owner/repo**.git - git remote, required for save/load

`~/.config/repo-config/owner/repo/` - dotfiles

#### Features
+   store repos config in dotfiles
    +   **exclude unwanted files from commit**
    +   you can symlink dotfiles to a special backup repo
    +   easy to perform search and commands

#### Config
```bash
$ echo "/.config" >> ~/.gitignore
```

optional. environment variables:
```bash
$ export REPO_CONFIG_HOME=~/.config/repo-config     # $XDG_CONFIG_HOME/repo-config by default
$ export REPO_CONFIG_DIR=.config                    # .config by default
```

#### Examples
```bash
$ cd path/to/repo
$ repo-config init .
$ ... # generate and edit config/tmp files
$ repo-config save .
.config/ saved to ~/.config/repo-config/owner/repo
$ repo-config load .
.config/ loaded from ~/.config/repo-config/owner/repo
```


symlink dotfiles to a special backup repository:

```bash
$ ln -fs path/to/backup-repository/repo-config ~/.config/repo-config
```

##### save/load multiple repos config
```bash
$ find ~/git -type d -maxdepth 1 -exec repo-config save {} \;
$ find ~/git -type d -maxdepth 1 -exec repo-config load {} \;
```

<p align="center">
    <a href="https://readme42.com/">readme42.com</a>
</p>
