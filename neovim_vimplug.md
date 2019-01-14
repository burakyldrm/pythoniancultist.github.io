---
layout: default
---

## Installing NeoVim + Vim-Plug

NeoVim is an upgraded version of vanilla Vim. Vim-Plug is a compatible package manager.

Installing NeoVim itself is trivial. Vim-Plug on the other hand can become troublesome. This guide will show you the exact steps on installing both without a hitch.

## Prerequisites

* Git
* Curl

## Install NeoVim

> sudo apt-get install neovim

Check if NeoVim is working by typing "nvim" on a terminal, then use ":q" command to quit NeoVim.

## Set up Vim-Plug

This is where it gets bothersome. While installation process is quite simple, caution must be taken, otherwise NeoVim will ignore the Vim-Plug.

Run the command below on a terminal:

>curl -fLo ~/.local/share/nvim/site/autoload/plug.vim --create-dirs \
>    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim

Check if "~/.local/share/nvim/site/autoload/plug.vim" directory and "plug.vim" exists

Move to the ".config" directory. Create a directory called "nvim" inside. Move to the "nvim" directory. Create an empty "init.vim" file with:

>echo "" >> init.vim

Run the command below on a terminal:

>curl -fLo ~/.config/nvim/autoload/plug.vim --create-dirs \
>    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim

Inside the "nvim" folder, open "init.vim" and paste the following inside:

>call plug#begin('~/.local/share/nvim/plugged')
>
>Plug 'junegunn/seoul256.vim'
>
>call plug#end()

Open NeoVim, write the ":PlugInstall" command, let it do its magic. Write the ":PlugStatus" command to see if everything is ok. Finally, write ":colo seoul256" to test your freshly installed plugin. Notice the color scheme difference? Congratulations you did it!. Now, go and experiment with new plugins!


[Back]({{ site.url }}/)
