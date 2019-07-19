---
title: configuring Vim
published: true
date: 2019-07-19
tags: ['Vim']
description: "Vim is a great editor. Even if you don't like it, it's a good thing to try it with a good configuration."
---

>Before doing anything, just go on Youtube to listen [Eric Burdon and War](https://www.youtube.com/watch?v=4nJ9I0dZ7Vo&t=59s), it will help you.

You can get the full [.vimrc without plugins](https://framagit.org/snippets/1861)!

## it's a great job!

_Vim_ configuration sits in one file (`~/.vimrc` by default) and a directory (`~/.vim` by default). The best way to configure _Vim_ is with a plugin manager such _Vundle_. Since version 8, _Vim_ has it's own plugin manager. Today, _Vim 8_ can be easily installed on a lot of distributions.

The great job is **I want a full IDE made with _Vim_!**

### reloading `~/.vimrc`

While you're listening Eric Burdon (his version of _nights in white satin_ is really beautiful), learn the first useful command to know while configuring _Vim_ and which is _how to reload the configuration file_. If your current buffer contains `~/.vimrc`, you just do:

```vim
:source %
```

where the `%` design the file in the current buffer. You can use the name of the file like that:

```vim
:source ~/.vimrc
```

You had to be careful, too much `source` can create some problems, variables are not always reset to their default values.

## getting help in _Vim_

To have more details about each elements of the configuration, ask _Vim_ with, for example, `:help nocompatible`.

## basic configuration

Before all, we had to tell _Vim_ that we don't want compatibility with old, very old, very very old versions of _vi_:

```vim
" no compatibility with old versions
" of vi, must be one of the first directives
set nocompatible
" modelines can be hatmful
set modelines=0
```

First, we set  line numbers and show the most we can on the ruler. Add this in your `~/.vimrc`:

```vim
" show line numbers
set number
set norelativenumber
" show line and column number of cursor position
set ruler
" show current mode
set showmode
set showcmd
" enable mouse on a terminal
" depending of the type of terminal emulation, X11 configuration, ...
" it can failed
set mouse=a
```
If you need to hide line numbers, just do 'set nonumber'.
Then, we enable indentation and syntax highlight following file type  :

```vim
" encoding...
set encoding=utf-8
" enable indentation
filetype plugin indent on
" and syntax highlight
syntax on
```

After that, I set tabulations as 4 spaces:

```vim
" tabulations
set tabstop=4
set softtabstop=0
set expandtab
set shiftwidth=4
```
