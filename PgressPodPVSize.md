k config set-context --current --namespace=tenant-paya

k exec -it  postgres-0 -- bash

du -sh /bitnami/

k exec -it  postgres-0 -n tenant-zarrindanehnakhlasia -- du -sh /bitnami/ 


kubectl get ns --no-headers -o custom-columns=":metadata.name"  | xargs -I{} kubectl exec -it  postgres-0 -n {} -- du -sh /bitnami/ 

kubectl get ns --no-headers -o custom-columns=":metadata.name"  | grep "tenant-" |xargs -I{} kubectl exec  postgres-0 -n {} -- du -sh /bitnami/

2>&1 | grep "No" | cut -d " " -f 5 |  xargs -I{} kubectl delete namespace {}

