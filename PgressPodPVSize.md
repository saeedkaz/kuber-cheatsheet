du -hd1 /bitnami/postgresql/data/ | sort -h 
ls -lh
kubectl get ns --no-headers -o custom-columns=":metadata.name"  | grep "tenant-" |xargs -I{} kubectl exec  postgres-0 -n {} --  bash -c "hostname -f && du -hd1 /bitnami/postgresql/data/ | sort -h" 2>/dev/null | sed 's/postgres-0.postgres-headless.//g' |sed 's/.svc.cluster.local//g'|sed 's/bitnami//g'| sed 's,/,,g'


kubectl get ns --no-headers -o custom-columns=":metadata.name"  | grep "tenant-" |xargs -I{} kubectl exec  postgres-0 -n {} --  bash -c "hostname -f && du -sh /bitnami/" 2>/dev/null | sed 's/postgres-0.postgres-headless.//g' |sed 's/.svc.cluster.local//g'|sed 's/bitnami//g'| sed 's,/,,g'

kubectl get ns --no-headers -o custom-columns=":metadata.name"  | grep "tenant-" |xargs -I{} kubectl exec  postgres-0 -n {} --  bash -c "hostname -f && du -sh /bitnami/" 2>/dev/null | sed 's/postgres-0.postgres-headless.//g' |sed 's/.svc.cluster.local//g'

k config set-context --current --namespace=tenant-paya

k exec -it  postgres-0 -- bash

du -sh /bitnami/

k exec -it  postgres-0 -n tenant-zarrindanehnakhlasia -- du -sh /bitnami/ 


kubectl get ns --no-headers -o custom-columns=":metadata.name"  | xargs -I{} kubectl exec -it  postgres-0 -n {} -- du -sh /bitnami/ 

kubectl get ns --no-headers -o custom-columns=":metadata.name"  | grep "tenant-" |xargs -I{} kubectl exec  postgres-0 -n {} -- du -sh /bitnami/

kubectl get ns --no-headers -o custom-columns=":metadata.name"  | grep "tenant-" |xargs -I{} kubectl exec  postgres-0 -n {} -- hostname -f

kubectl get ns --no-headers -o custom-columns=":metadata.name"  | grep "tenant-" |xargs -I{} kubectl exec  postgres-0 -n {} --  bash -c "hostname -f && du -sh /bitnami/" 2>/dev/null

