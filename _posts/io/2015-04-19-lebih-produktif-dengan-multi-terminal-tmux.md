---
layout: post
title: "Lebih Produktif Dengan Multi Terminal TMUX"
shorttitle: "Produktif Dengan TMUX"
description: "Cara Install TMUX di Linux dan tips lebih produktif dengan multi terminal."
category: io
tags: [linux]
---

## Install TMUX

    sudo apt-get install TMUX
    tmux

## Shorcut TMUX
Semua ada di `CTRL+b ?` dan intinya `C-b` adalah `CTRL+b`

## Start TMUX di setiap login shell

Pada `~/.bashrc` atau `~/.zshrc` tergantung shell yang digunakan

    # If not running interactively, do not do anything
    [[ $- != *i* ]] && return
    [[ -z "$TMUX" ]] && exec tmux

## MISC

- https://wiki.archlinux.org/index.php/Tmux#Autostart_tmux_with_default_tmux_layout
- https://danielmiessler.com/study/tmux/
