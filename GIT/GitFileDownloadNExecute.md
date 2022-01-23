# Git File Download and Execute

## download from a public repo (must use API)

bash <(curl -s http://mywebsite.com/myscript.txt)

## download from a private repo (must use API)

```bash
#!/usr/bin/env bash

TOKEN="<INSERTACCESSTOKENHERE>"
OWNER="<github-user>"
REPO="<github-repo-name>"
FILE_PATH="scripts/setup.sh"
FILE="https://api.github.com/repos/$OWNER/$REPO/contents/$FILE_PATH"

curl --header "Authorization: token $TOKEN" \
     --header 'Accept: application/vnd.github.v3.raw' \
     --remote-name \
     --location $FILE_PATH
```



## Make executable
```bash
git ls-files "*.sh" | xargs git update-index --add --chmod=+x
```
