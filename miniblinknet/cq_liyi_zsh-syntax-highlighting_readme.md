zsh-syntax-highlighting [![Build Status][build-status-image]][build-status-travis]
=======================

**[Fish shell][fish]-like syntax highlighting for [Zsh][zsh].**

*Requirements: zsh 4.3.11+.*

[fish]: http://www.fishshell.com/
[zsh]: http://www.zsh.org/

This package provides syntax highlighting for the shell zsh.  It enables
highlighting of commands whilst they are typed at a zsh prompt into an
interactive terminal.  This helps in reviewing commands before running
them, particularly in catching syntax errors.

Some examples:

Before: [![Screenshot #1.1](images/before1-smaller.png)](images/before1.png)
 
After:&nbsp; [![Screenshot #1.2](images/after1-smaller.png)](images/after1.png)

Before: [![Screenshot #2.1](images/before2-smaller.png)](images/before2.png)
 
After:&nbsp; [![Screenshot #2.2](images/after2-smaller.png)](images/after2.png)

Before: [![Screenshot #3.1](images/before3-smaller.png)](images/before3.png)
 
After:&nbsp; [![Screenshot #3.2](images/after3-smaller.png)](images/after3.png)

Before: [![Screenshot #4.1](images/before4-smaller.png)](images/before4-smaller.png)
 
After:&nbsp; [![Screenshot #4.2](images/after4-smaller.png)](images/after4-smaller.png)



How to install
--------------

See [INSTALL.md](INSTALL.md).


FAQ
---

### Why must `zsh-syntax-highlighting.zsh` be sourced at the end of the `.zshrc` file?

`zsh-syntax-highlighting.zsh` wraps ZLE widgets.  It must be sourced after all
custom widgets have been created (i.e., after all `zle -N` calls and after
running `compinit`).  Widgets created later will work, but will not update the
syntax highlighting.

### Does syntax highlighting work during incremental history search?

Highlighting the command line during an incremental history search (by default bound to
to  Ctrl+R  in zsh's emacs keymap) requires zsh 5.4 or newer.

Under zsh versions older than 5.4, the zsh-default [underlining][zshzle-Character-Highlighting]
of the matched portion of the buffer remains available, but zsh-syntax-highlighting's
additional highlighting is unavailable.  (Those versions of zsh do not provide
enough information to allow computing the highlighting correctly.)

See issues [#288][i288] and [#415][i415] for details.

[zshzle-Character-Highlighting]: http://zsh.sourceforge.net/Doc/Release/Zsh-Line-Editor.html#Character-Highlighting
[i288]: https://github.com/zsh-users/zsh-syntax-highlighting/pull/288
[i415]: https://github.com/zsh-users/zsh-syntax-highlighting/pull/415

### How are new releases announced?

There is currently no "push" announcements channel.  However, the following
alternatives exist:

- GitHub's RSS feed of releases: https://github.com/zsh-users/zsh-syntax-highlighting/releases.atom
- An anitya entry: https://release-monitoring.org/project/7552/


How to tweak
------------

Syntax highlighting is done by pluggable highlighter scripts.  See the
[documentation on highlighters](docs/highlighters.md) for details and
configuration settings.

[build-status-image]: https://travis-ci.org/zsh-users/zsh-syntax-highlighting.svg?branch=master
[build-status-travis]: https://travis-ci.org/zsh-users/zsh-syntax-highlighting



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e8d240f43a3c96688917eafdd1a0557eaa09844e13e2a1375699d82de0de8eae00bab98c5fa39972123ae14897e2c1c44e9dc6d686f74ed0a49a580d5b0cdd8ad)