```
AWS_ACCESS_KEY_ID=.....
AWS_SECRET_ACCESS_KEY=...

kubectl -n kube-system create secret generic alb-ingress-iam \
  --from-literal=AWS_ACCESS_KEY_ID=${AWS_ACCESS_KEY_ID} \
  --from-literal=AWS_SECRET_ACCESS_KEY=${AWS_SECRET_ACCESS_KEY} \
  --dry-run -o yaml > base/secret-alb-ingress-iam.yaml

kustomize build overlays | kubectl apply -f -
```
