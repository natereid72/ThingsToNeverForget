## Things to Stop Googling

### Find the stuck CRD when a NS won't delete

for ns in $(kubectl get ns --field-selector status.phase=Terminating -o jsonpath='{.items[*].metadata.name}'); do  kubectl get ns $ns -ojson | jq '.spec.finalizers = []' | kubectl replace --raw "/api/v1/namespaces/$ns/finalize" -f -; done

### Configure prometheus operated for ingress path

Edit the prometheus object and configure these:
    externalUrl: http://example.com/prometheus
    routePrefix : prometheus/
