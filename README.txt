+++ header
@file: tmux-conf/README.txt
@date:
- created on 2025-04-05
- updated on 2025-04-05
@author:
- madpang
+++

=== Introduction

This repo. contains the tmux configuration file that is gradually refined during my daily work.

=== Usage

+++ cmd
cp tmux-conf.txt ~/.tmux.conf
# or you can create a symbolic link
+++

=== Note

--- Shell

Many shells (e.g. bash, zsh) have multiple configuration files, and whether each one is loaded is differentiated by the shell type (login or non-login) and the shell mode (interactive or non-interactive).
For example, when using bash, a login shell will source `~/.profile` (or `~/.bash_profile` if it exists), while a non-login shell will source `~/.bashrc`.

When using tmux, the default command is actually `bash -l`, which forces the shell to be a login shell, this means that besides `~/.bashrc`, `.profile` will also be sourced.
But this will cause an issue when you want to set environment variable, e.g., `export PATH=/some/path:$PATH`---that is, the PATH will contain duplicate entries---since `.profile` is effectively sourced twice.
To circumvent this, we can set the default command to `exec bash` in the tmux configuration file to make it launch a non-login shell.
Now you can set the environment variable in `~/.profile`, tmux launched session will inherit the environment variable w/o sourcing it again.

--- Keyboard

I am HHKB user w/ a Emacs background, and the keybinding reflects my flavor.

--- Color

I have tuned the status bar color with an inspiration from the [Aston Martin Valkyrie] Hypercar---that blueish green is so cool so memorable!
+++ img
[Aston Martin Valkyrie](media/Aston_Martin_Valkyrie.webp)
+++
NOTE, image is obtained from the official website of Aston Martin.

--- Font

I am using [JetBrains Mono] font, which is a modern free and open-source typeface, what is more, I like its ligature design very much---yes, I am using ligature in terminal!
