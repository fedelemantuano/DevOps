# Git

### Config List
    git config --global --list
    git config --local --list

### SSL no verify 
    git config --global --unset http.sslVerify
    git config --global http.sslVerify false
 
### Git Config file
    [http "<matching url>"]
        proxy = <url>
    [http]
        proxy = <url>
        sslverify = false
