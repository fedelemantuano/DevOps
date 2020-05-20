# Openshift cli

GitHub repo: [openshift/origin](https://github.com/openshift/origin/releases)  
Site: [OKD](https://www.okd.io/download.html)

## Install oc cli

```bash
# example ver 3.11
wget https://github.com/openshift/origin/releases/download/v3.11.0/openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit.tar.gz
tar -xf openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit.tar.gz
mv ./openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit/oc  /usr/local/bin/
mv ./openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit/kubectl  /usr/local/bin/
chmod 755 /usr/local/bin/oc
chmod 755 /usr/local/bin/kubectl
rm -f openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit.tar.gz
rm -rf openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit
```

## cli completion

    source <(oc completion bash)
    source <(oc completion zsh)
    
    oc completion bash > oc_completion.sh
    # In .bashrc
    source oc_completion.sh
