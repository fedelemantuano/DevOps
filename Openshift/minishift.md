#

## MiniShift commands
    minishift start/stop
    minishift console --url # to get the openshift console url 
    minishift delete -f     # to remove the generated VM
    minishift delete --force --clear-cache      # to remove the generated VM
    minishift start --show-libmachine-logs -v5  # to start with debug log
    
    
## shell (as minikube)
    login: docker
    pass: tcuser
    # switch to root:
    # sudo su
