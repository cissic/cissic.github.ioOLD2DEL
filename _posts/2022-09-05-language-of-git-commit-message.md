---
author:
- cissic
date: '\<2022-09-08 czw\>'
description: Not presented description included in the final document
tags: linux git bash
title: English as the default language of git commit comments
---

How to set English as the default language of git commit comments
-----------------------------------------------------------------

The following is based on [this
post](https://stackoverflow.com/a/10872202).

Add these lines to your `~/.bashrc`, `~/.bash_profile` or `~/.zprofile`
to force git to display all messages in English:

::: {.SOURCE}
\#alias git=\'LANG=en~US~ git\' alias git=\'LANG=en~GB~ git\'
:::

bash

The alias needs to override `LC_ALL` on some systems, when the
environment variable `LC_ALL` is set, which has precedence over `LANG`.
See the \[UNIX Specification - Environment
Variables\](<http://pubs.opengroup.org/onlinepubs/7908799/xbd/envvar.html>)
for further explanation.

``` {.example}
# Set Git language to English
#alias git='LC_ALL=en_US git'
alias git='LC_ALL=en_GB git'
```

In case you added these lines to `~/.bashrc` the alias will be defined
when a new interactive shell gets started. In case you added it to
`~/.bash_profile` the alias will be applied when logging in.
