Use folloing to delete all empty namespaces

kubectl get ns --no-headers -o custom-columns=":metadata.name"  | xargs -I{} kubectl  get all -n {} 2>&1 | grep "No" | cut -d " " -f 5 |  xargs -I{} kubectl delete namespace {}

you can list empty namespaces by this

kubectl get ns --no-headers -o custom-columns=":metadata.name"  | xargs -I{} kubectl  get all -n {} 2>&1 | grep "No" | cut -d " " -f 5
