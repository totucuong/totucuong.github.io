---
layout: post
title:  "YouCompleteMe with Vim8 on MacOS"
date:   2020-05-10
author: To Tu Cuong
---
I'm switching my IDE from Visual Code to Vim8. Vim8 coupled with plugins like FZF or CtrlP (fuzzy file search) or jedi-python (python editing) provides a lot of functionalities like any modern IDE. The nice thing is that it is quite easy to remember all those shortcuts.

I'm always bad at remembering those shortcuts from different IDEs. I tried PyCharm, then Microsoft Visual Code. Each of them has different shortcuts, which confused me a lot.

Another problem is that I have a Macbook and uses Ubuntu for my server, running machine learning code. Sometimes I need to edit my code directly on the server for quick experiment. There the only option was vim. So by using vim, I will have my familar IDE everywhere.

Of all plugins, I like YouCompleteMe the most. YouCompleteMe installation instruction is limited to using VBundle. In this blog, I'll walk you through how to install it semiautomatic using vim-plug, another package manager of vim.

First, you need to clone YouCompleteMe and put it your ~/.vim/plugged. This is assumed that you are using vim-plug to manages your plugins.

    cd ~/.vim/plugged 
    git clone https://github.com/ycm-core/YouCompleteMe.git

Then, you go to the YouCompleteMe cloned repo and compile it:

    cd ~/YouCompleteMe
    git submodule update --init --recursive
    /usr/bin/python3 install.py

Note that you need to use the python3 that comes with MacOS. Using conda python will mess the compiling up. 
Finally, you can add the following line to your ~/.vimrc:
    
    Plug 'ycm-core/YouCompleteMe'

Remember to excute "PlugInstall" within vim to install YouCompleteMe. That's it. I hope that you enjoy vim and save up 1 or 2 hours of searching how to install YouCompleteMe for vim8 on MacOS :(.
 
