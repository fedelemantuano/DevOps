# VI
  
    vi ~/.vimrc                             # per user
    vi /etc/vimrc or /etc/vim/vimrc.local   # global
    vi /etc/vim/vimrc.tiny                  # global for Debian
    # NOTE: /etc/vim/vimrc refers to /etc/vim/vimrc.local and should not be edited
example:  

    set nocompatible  # Arrows don't print letters in insert mode
    set backspace=2
    set tabstop=4 softtabstop=0 expandtab shiftwidth=4 smarttab
    set noautoindent
    set paste
    
# SSH

    vi ~/.ssh/config        # per user
    vi /etc/ssh/ssh_config  # global
example:  

    Host *
        StrictHostKeyChecking no
        CheckHostIP no
    
    Host 192.168.0.*
        IdentityFile ~/.ssh/id_rsa_private
      
# ENV VARS

## /etc/environment

    vi /etc/environment

works only with programs compiled with PAM, to list supported executable launch:
    
    grep -l pam_env /etc/pam.d/*

Only export var=value lines

## /etc/profile.d/\*.sh

    vi /etc/profile.d/file.sh
    
POSIX standard, executes/evaluates the script file at bash login


    
