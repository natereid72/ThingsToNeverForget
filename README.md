## Things to Stop Googling

### Find the stuck CRD when a NS won't delete

kubectl api-resources --verbs=list --namespaced -o name | xargs -n 1 kubectl get --show-kind --ignore-not-found -n <namespace>

kubectl patch <type/name> -n <namespace> -p '{"metadata":{"finalizers":[]}}' --type=merge


### Configure prometheus operated for ingress path

Edit the prometheus object and configure these:

externalUrl: http://example.com/prometheus

routePrefix : prometheus/

Do same for alertmanager

### vSphere VCSA/ESXI setting for Intel CPU issue
https://kb.vmware.com/s/article/55806
