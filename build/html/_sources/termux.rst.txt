======
Termux
======

Address
=======

* https://mirrors.sosconf.org/termux

Introduction
============

Termux is a terminal emulator and Linux environment bringing powerful terminal access to Android. No root is required, runs on internal storage (not on an SD card).

It comes with a package manager that allows you to install many modern development and system maintenance tools. like what:

* neovim
* tmux
* zsh
* clang
* gcc
* weechat
* irssi
* …

Architecture
============

* ARM
* AArch64
* i686
* x86_64

Instructions for Use
====================

In the newer version of Termux, the official graphical interface (TUI) is provided to replace the image semi-automatically, and it is recommended to use this method to avoid other risks. Execute the following command in Termux
::

  termux-change-repo

Guided by the graphical interface, use the built-in arrow keys to move up and down.
The first step uses spaces to select the repository that needs to be replaced, and then selects the TUNA/BFSU image source in the second step. After confirming that there is no error, enter the mirror source and automatically complete the replacement.

If that no work, you can use the following commands to replace the source:

::

  sed -i 's@^\(deb.*stable main\)$@#\1\ndeb https://mirrors.sosconf.org/termux/termux-packages-24 stable main@' $PREFIX/etc/apt/sources.list
  sed -i 's@^\(deb.*games stable\)$@#\1\ndeb https://mirrors.sosconf.org/termux/game-packages-24 games stable@' $PREFIX/etc/apt/sources.list.d/game.list
  sed -i 's@^\(deb.*science stable\)$@#\1\ndeb https://mirrors.sosconf.org/termux/science-packages-24 science stable@' $PREFIX/etc/apt/sources.list.d/science.list
  apt update && apt upgrade


Links
========

:Termux Homepage: https://termux.com/
:FDroid: https://f-droid.org/zh_Hant/packages/com.termux
:Google Play: https://play.google.com/store/apps/details?id=com.termux
