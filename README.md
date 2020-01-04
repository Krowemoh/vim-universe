# vim-universe
Vim and Universe Workflow

Add keybindings to format and compile Basic programs directly from vim.

I've also added my basic vimrc to github as well, the only thing of interest is that I automatically set syntax highlighting for any basic programs in BP or MPROCLIB.

## Requirements

Feel free to take a peek at the python programs, all it does is cd into what it assumes/hopes is Universe account folder and then attempts to run a BASIC command.

This does mean however that you are editing the BASIC program in the folder it resides, and that it is one level deeper than the account.

So you would be editing TEST.UNIVERSE sitting in /home/ACCOUNT-NAME/BP where ACCOUNT-NAME is a Universe account.

This could probably be improved where we can look at the path of the file and UV.ACCOUNT to LOGTO to the correct place but this was a quick utility taking advantage of the fact that we can script Universe behavior directly from Linux. 

## Installation

    
    mkdir -p ~/.vim/u2py
    cd ~/.vim/u2py/
    wget XXX
    wget XXX
    chmod +x format.py
    chmod +x basic.py
  
Add the below to your ~/.vimrc file:
    
    "Run scripts to format or compile programs
    "autoread is to refresh any changes
    set autoread
    command F :exec '!~/.vim/u2py/format.py ' . expand("%")
    command F :exec '!~/.vim/u2py/basic.py ' . expand("%")
    
## Use

Enter `:F` to format the basic program. This will print out something like the following:
    
    1 lines long.
    
    Formatting item "TEST".
    
    "TEST" "TEST" 1L, 21C
  
Enter `:B` to compile the basic program. 

Success will print out something like:
    
    Compiling: Source = 'BP/TEST', Object = 'BP.O/TEST'
    
    Compilation Complete.
  
Failure will produce:
    
    Compiling: Source = 'BP/TEST', Object = 'BP.O/TEST'
    
    000001          SPRINT "HELLO!"
                    ^
    String Constant unexpected, Was expecting: Assignment Operator
    
    1 Errors detected, No Object Code Produced.
  
  ## Issues
  
  Feel free to get in touch if you have an issue.

