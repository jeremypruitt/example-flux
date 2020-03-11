# Use this to revert the last commit. Useful for toggling.
git revert $( git rev-parse HEAD )
git push origin master

# Tail logs for the klux pod
kubectl -n flux get pods
kubectl logs flux-5db7484d7-k9tkc -n flux -f

# Grab the initial password for ArgoCD, which is the argo-cd-server name
$ kubectl get pods  -l app.kubernetes.io/name=argocd-server -o name \
  | cut -d'/' -f 2

# Find the ArgoCD service
kubectl get services -A

# Port forward to the argocd-server
kubectl port-forward svc/argocd-server 8088:443

# Open you browser and navigate to https://localhost:8088
