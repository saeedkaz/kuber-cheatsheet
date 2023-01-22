k config set-context --current --namespace=tenant-paya
k exec -it  postgres-0 -- bash
du -sh /bitnami/

k exec -it  postgres-0 -n tenant-zarrindanehnakhlasia -- du -sh /bitnami/ 
