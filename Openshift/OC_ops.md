# OPS

## Remote shell

    oc rsh <pod>
    
## Move file from/to pods
    #from pod
    oc rsync <pod-name>:/remote/dir/filename ./local/dir
    # to pod
    oc rsync ./local/dir <pod-name>:/remote/dir
