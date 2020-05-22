# Minishift

## Minishift commands
    minishift setup-cdk                         # creates $USER_HOME\.minishift
    minishift start/stop
    minishift console --url # to get the openshift console url 
    ### start debug
    minishift start --show-libmachine-logs -v5  # to start with debug log located in folder: ~/.minishift/cache

    ### config hyper-v
    minishift config set hyperv-virtual-switch "ExtNet"
    minishift config set vm-driver hyperv
    ### config virtualbox
    minishift config set vm-driver virtualbox

    ### delete
    minishift delete -f                         # to remove the generated VM in $USER_HOME\.minishift
    minishift delete --force --clear-cache      # to remove the generated VM and all $USER_HOME\.minishift

## shell (as minikube)
    login: docker
    pass: tcuser
    # switch to root:
    # sudo su

## COMMON ERRORS
    
#### Check release FAIL
    C:\Users\Unknown>minishift start
    -- Starting profile 'minishift'
    -- Check if deprecated options are used ... OK
    -- Checking if https://mirror.openshift.com is reachable ... OK
    -- Checking if requested OpenShift version 'v3.11.43' is valid ... FAIL
    # FIX
    minishift config set skip-check-openshift-release true
    
    
