#

## MiniShift commands
    minishift start/stop
    minishift console --url # to get the openshift console url 
    ### start debug
    minishift start --show-libmachine-logs -v5  # to start with debug log located in folder: ~/.minishift/cache

    ### config hyper-v
    minishift config set hyperv-virtual-switch "ExtNet"
    minishift config set vm-driver 
    ### config virtualbox
    minishift config set vm-driver virtualbox 

    ### delete
    minishift delete -f     # to remove the generated VM
    minishift delete --force --clear-cache      # to remove the generated VM

## shell (as minikube)
    login: docker
    pass: tcuser
    # switch to root:
    # sudo su
