# Cluster ADMIN

## Node status

    oc get nodes
    oc describe node <node-name>


## Delete all evicted pods in openshift

### for the current namespace
    eval "$(oc get pods -o json | jq -r '.items[] | select(.status.phase == "Failed" and .status.reason == "Evicted") | "oc delete pod --namespace " + .metadata.namespace + " " + .metadata.name')"
    # no jq
    for evicted in $(oc get pods | grep "Evicted" | awk '{print $1}'); do oc delete pod ${evicted}; done

### for all namespaces
    eval "$(oc get pods -o json --all-namespaces | jq -r '.items[] | select(.status.phase == "Failed" and .status.reason == "Evicted") | "oc delete pod --namespace " + .metadata.namespace + " " + .metadata.name')"
