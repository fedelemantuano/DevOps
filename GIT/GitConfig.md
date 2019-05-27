# Git

### Config List
    git config --list --global --show-origin
    git config  --list --local --show-origin

### SSL no verify 
    git config --global --unset http.sslVerify
    git config --global http.sslVerify false
 
### Git Config file
    [user]
	    name = <Name Surname>
	    email = <mymail@gmail.com>
        username = <nickname>
    [http "<matching url>"]
        proxy = <url>
        sslverify = false
    [http]
        proxy = <url>
        sslverify = true
