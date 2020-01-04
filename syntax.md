# Syntax Highlighting in Universe

Add highlighting automatically to basic programs.

The syntax file is from: https://www.vim.org/scripts/script.php?script_id=2143

## Installation
    
    mkdir -p ~/.vim/syntax
    cd ~/.vim/syntax/
    wget https://raw.githubusercontent.com/Krowemoh/vim-universe/master/syntax/unibasic.vim

Add the below to your ~/.vimrc file:
    
    "Anything under BP, and MPROCLIB will be set to use the syntax highlighter
    autocmd BufRead,BufNewFile */BP/* set syntax=unibasic
    autocmd BufRead,BufNewFile */MPROCLIB/* set syntax=unibasic
