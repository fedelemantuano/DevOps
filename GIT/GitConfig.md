# Git

### Config List
    git config --list --global --show-origin
    git config --list --system --show-origin
    git config  --list --local --show-origin

### SSL no verify 
    git config --global --unset http.sslVerify
    git config --global http.sslVerify false
 
### Git Config file
    [user]
	name = <Name Surname>
	email = <mymail@gmail.com>
        username = <nickname>
    [http]
        proxy = <url>
        sslverify = true
    [http "<matching url>"]
        proxy = <url>
        sslverify = false


### Git Config file priority

    /etc/gitconfig		# system
    ~/.config/git/config	# global
    ~/.gitconfig		# global
    ./.git/config		# local
    
    
