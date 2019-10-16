# VI
  
    vi ~/.vimrc                             # per user
    vi /etc/vimrc or /etc/vim/vimrc.local   # global
    # NOTE: /etc/vim/vimrc refers to /etc/vim/vimrc.local and should not be edited
example:  

    set nocompatible  # Arrows don't print letters in insert mode
    set backspace=2
    set tabstop=4 softtabstop=0 expandtab shiftwidth=4 smarttab
    
    
# SSH

    vi ~/.ssh/config        # per user
    vi /etc/ssh/ssh_config  # global
example:  

    Host *
        StrictHostKeyChecking no
        CheckHostIP no
    
    Host 192.168.0.*
        IdentityFile ~/.ssh/id_rsa_private
      
