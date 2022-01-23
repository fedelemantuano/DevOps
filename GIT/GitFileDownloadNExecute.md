# Git File Download and Execute

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
