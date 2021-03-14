# Simplified IEEE Template [![Build Status](https://circleci.com/gh/latextemplates/IEEE/tree/master.svg?style=shield)](https://circleci.com/gh/latextemplates/IEEE/)

> Quick start for modern LaTeXing for an IEEE conference, based on the [Manuscript Template for Conference Proceedings](http://u.720life.cn/g/cb537e5fb4c73a47ac98a214ee6354430fccae2634d975cad75960ac19937adf6b1a3e591930a6e16fda658e87708d41e0c8ecd5fed9c353b1f45f304b0e276872244f4dfcc187efc27dbc3c77298aaf).

The official template is distributed via CTAN as the [IEEEtran package](http://u.720life.cn/g/b4c5d8488d0fa6da4fb83cece8f5f61133e38196ba031bd317c9baa8f11ead0f), which is actively maintained.
However, de-facto configurations (hyperref) and modern features of latex (microtype) are not configured.
This page does it.

This template is for the computer science conferences.
It is based on the `bare_conf_compsoc.tex` distributed by IEEE.
In case you need other configurations, please adapt `paper-conference.tex` or `paper-conference-compsoc.tex`.

Examples:

- [paper-conference.pdf](http://u.720life.cn/g/67d286a29581aeb9c4846e48fd5eee7ec0c2a8c2f74b42da357594bb338b648f3f5190b196188f67a0a67da71dc240b4cc9350d5ba5ac008b0ed8c323c2eeb92) - regular conference paper.
- [paper-conference-minted.pdf](http://u.720life.cn/g/67d286a29581aeb9c4846e48fd5eee7ec0c2a8c2f74b42da357594bb338b648f3f5190b196188f67a0a67da71dc240b42de4f60570845aa104b8f2880dde5b6e405fc55f2466b89c98040714d95a343d) - conference paper showing minted in action.
- [paper-conference-compsoc.pdf](http://u.720life.cn/g/67d286a29581aeb9c4846e48fd5eee7ec0c2a8c2f74b42da357594bb338b648f3f5190b196188f67a0a67da71dc240b44a867baea5598801e9331720e861bbe6087d6d9d85066732ff9e16c12ef3258e) - papers for IEEE Computer Society conference papers.


## Attention
Some conferences distribute a `IEEEtran.cls` V1.7a dated 2007 and a parameter `compsocconf`.
**The parameter `compsocconf` was NEVER included in Michael Shell's IEEEtran.cls file. It is unclear, who did this patch and why it is around in the wild.**

The most recent version is V1.8b and automatically distributed over CTAN, because it is actively maintained by Michael Shell at  .
A full changelog is available at  .

```
 2014/09/17 V1.8a (MDS) changes:

 1) Extensive rework of the compsoc mode to comply with the latest standards
    of the IEEE Computer Society.
```

The class parameter `compsocconf` never existed officially.
One has to use `conference, compsoc`, because the parameters are "orthogonal": Either "conference" or "journal", either "compsoc" or not.
With a modern IEEEtran.cls, you'll get

```
LaTeX Warning: Unused global option(s):
    [compsocconf].
```

When using the 2007 version or the most recent version with (the unhandled) `compsocconf`, you'll get [paper-conference.pdf](http://u.720life.cn/g/67d286a29581aeb9c4846e48fd5eee7ec0c2a8c2f74b42da357594bb338b648f3f5190b196188f67a0a67da71dc240b4cc9350d5ba5ac008b0ed8c323c2eeb92) instead of [paper-conference-compsoc.pdf](http://u.720life.cn/g/67d286a29581aeb9c4846e48fd5eee7ec0c2a8c2f74b42da357594bb338b648f3f5190b196188f67a0a67da71dc240b44a867baea5598801e9331720e861bbe6087d6d9d85066732ff9e16c12ef3258e).
That differs significantly in the style used for section headings.

IEEE distributes their templates at  .
With the update of July 2017, the archive   contains both `bare_conf.tex` and `bare_conf_compsoc.tex`.
Thus, the conference should state which option to use.

All in all, the distributions of IEEEtran from 2007 are roughly equivalent to `\documentclass[conference]{IEEEtran}` (and version V1.8b), which **does not comply** with IEEE's rules for computer science conferences, because the `compsoc` option is missing.

Hence, **double check with your conference whether you have to use `compsoc` or not.**

Statement from IEEE:

> Please note that, as stated on the webpage  . "IEEE does not require a specific format for their conference articles". Thus, we dot not purport that the "compsoc" is a requirement for publishing conference papers with us.


## TOC

 

- [Features](#features)
- [Quick start](#quick-start)
- [Tool hints](#tool-hints)
- [Using the template with your git repository](#using-the-template-with-your-git-repository)
- [FAQ](#faq)
  * [Q: I get the error `! pdfTeX error (font expansion): auto expansion is only possible with scalable fonts.`](#q-i-get-the-error---pdftex-error-font-expansion-auto-expansion-is-only-possible-with-scalable-fonts)
  * [Q: I have questions on the IEEEtran class itself.](#q-i-have-questions-on-the-ieeetran-class-itself)
  * [Q: How can I reformat my .tex files?](#q-how-can-i-reformat-my-tex-files)
  * [Q: How I want to obey the one-sentence-per-line rule.](#q-how-i-want-to-obey-the-one-sentence-per-line-rule)
- [Links](#links)

 

## Features

 * Provides skeletal [paper-conference.tex](paper-conference.tex) and [paper-conference-compsoc.tex](paper-conference-compsoc.tex) files.
 * Generated PDF allows for copy and paste of text without getting words with ligatures such as "workflow" destroyed.
   This is enabled by the [cmap] package, which encodes ligatures (such as fl) using unicode characters.
 * Support of hyperlinked references without extra color thanx to [hyperref].
 * Better breaking of long URLs.
 * Support for `\powerset` command.
 * Support todos as pdf annotations. This is enabled by the [pdfcomment] package.
 * [microtypographic extensions](http://u.720life.cn/g/dd89c30c838202995b0edd9adbec174272b805b1cf9b1252d3ae5e45ea9ce76eee14f2c6bf18bf3e036de7466c3cf967) for a better look of the paper.
 * Adds modern packages such as [microtype], [cleveref], [csquotes], [booktabs], [paralist], [hyperref], [hypcap], [upquote].
 * Shows how IEEE copyright notice can be added.
 * Optional: Support for [minted] package. Prepared in `paper-conference-minted.tex`.
 * Ready-to-go configuration for [latexindent].

## Quick start

 * Click on `Download ZIP` or [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cca8110e18592e345f6c676158f5f121c9279f6eda4535901997ecc49c4eb2e2a2b476753cc0f9de28f316ba3d787395).
 * Extract `master.zip` in the folder where you want to write your paper.
 * In case you are working in the computer science field: Edit [paper-conference-compsoc.tex](paper-conference-compsoc.tex).
 * In case you are NOT working in the computer science field: Edit [paper-conference.tex](paper-conference.tex).
 * `latexmk paper-conference-compsoc` OR `latexmk paper-conference`.

## Tool hints

There is currently no official biblatex support.
A first step towards that is done at the [biblatex-ieee package](http://u.720life.cn/g/b4c5d8488d0fa6da4fb83cece8f5f6116b2373585e1a22ffbc1c22e4dc223cb0f44405db27fa79e02dd40a710b86c21d).

MiKTeX installation hints are given at  .

- Grammar and spell checking is available at [TeXstudio].
  Please download [LanguageTool] (Windows: `choco install languagetool`) and [configure TeXstudio to use it](http://u.720life.cn/g/e01374fd96d43b41607f20aaa0f992abfdb0b11000d9e887e44af9805dc3372307b313b93355a252e3c72fe8dc74be83c391c08ee5a8b2e5115e4c502ca0165913d9dca66f74cc52212ecca4f6aa3dcf).
  Note that it is enough to point to `languagetool.jar`.
  **If TeXstudio doesn't fit your need, check [the list of all available LaTeX Editors](http://u.720life.cn/g/36d405cc75811ed15956fd8b7f3974c4861d3c21dd02040b7e54250bde94e74c97894b8989d63b593e1c83a13ce10ded7cb6e1139db96c47ee36885ff816d0f8).**
- Use [JabRef] to manage your bibliography (Windows: `choco install jabref`).


In case you want to get started using minted, do following steps:

1. Install python: `choco install python` - that uses [chocolatey](http://u.720life.cn/g/9bc921a271360009e6bb627886d4751c06bfd21a3b46577e8172a58e5e7773ac) to install Python
2. Install [pygments]: `pip instal pygments` - that uses the Pyhton package manager to install the pygments library
3. When latexing, use `-shell-escape`: `pdflatex -shell-escape paper`.
   You can also just execute `latexmk paper`.

## Using the template with your git repository

1. Initialize your git repository as usual
2. Add this repository as upstream: `git remote add upstream https://github.com/latextemplates/IEEE.git`
3. Merge the branch `upstream/master` into your `master` branch: `git merge upstream/master`.

After that you can use and push the `master` branch as usual.
Notes on syncing with the upstream repository [are available from GitHub](http://u.720life.cn/g/1f425b0b33da40ebdfbaffd56fc94509ec09346c8015e0ae429751be8b3a78a56bae08a665d60f2a64a824682665596c).

## FAQ

### Q: I get the error  `! pdfTeX error (font expansion): auto expansion is only possible with scalable fonts.`

Install the `cm-super` package using the MiKTeX package manager. Then, run `initexmf --mkmaps` on the command line. (Long description: http://tex.stackexchange.com/a/324972/9075)


### Q: I have questions on the IEEEtran class itself.

The author of the class offers a large FAQ at  .
Please read on there.


### Q: How can I reformat my .tex files?

Execute `latexindent -l -s -sl -w paper.tex`


### Q: How I want to obey the one-sentence-per-line rule.

Execute `latexindent -m -l -s -sl -w paper.tex`.
Attention! This is work in progress and does not always produce best results.

## Links

 * German: Hinweise zu Ausarbeitungen:  
 * Other templates:  

  [booktabs]: https://www.ctan.org/pkg/booktabs
  [cleveref]: https://ctan.org/pkg/cleveref
  [cmap]: https://www.ctan.org/pkg/cmap
  [csquotes]: https://www.ctan.org/pkg/csquotes
  [hypcap]: https://www.ctan.org/pkg/hypcap
  [hyperref]: https://ctan.org/pkg/hyperref
  [latexindent]: https://ctan.org/pkg/latexindent
  [microtype]: https://ctan.org/pkg/microtype
  [minted]: https://ctan.org/pkg/minted
  [newtx]: https://ctan.org/pkg/newtx
  [paralist]: https://www.ctan.org/pkg/paralist
  [pdfcomment]: https://www.ctan.org/pkg/pdfcomment
  [upquote]: https://www.ctan.org/pkg/upquote

  [JabRef]: https://www.jabref.org
  [LanguageTool]: https://languagetool.org/
  [TeXstudio]: http://texstudio.sourceforge.net/
  [pygments]: http://pygments.org/



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edb31a0af5c322354685f3c32fbcf9b927a2a4842b42ba5347b178812748cf28b34795efc10902f2e1b69fbdef69bdda3)