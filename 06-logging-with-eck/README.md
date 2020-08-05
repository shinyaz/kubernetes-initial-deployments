# Logging with ECK

## Quick Installation

```
kubectl apply -f 01-all-in-one.yaml
kubectl apply -f 02-namespace.yaml
kubectl apply -f 03-elasticsearch.yaml
kubectl apply -f 04-kibana.yaml
kubectl apply -f 05-fluent-bit-service-account.yaml
kubectl apply -f 06-fluent-bit-role.yaml
kubectl apply -f 07-fluent-bit-role-binding.yaml
kubectl apply -f 08-fluent-bit-configmap.yaml
kubectl apply -f 09-fluent-bit-ds.yaml

# Get elastic password and update 10-elastic-curator.yaml
kubectl -n logging get secret logging-es-elastic-user -o=jsonpath='{.data.elastic}' | base64 --decode
vi 10-elastic-curator.yaml
# -> Update CHANGE_ELASTIC_PASSWORD

kubectl apply -f 10-elastic-curator.yaml
kubectl apply -f 11-logging-kb-http-public.yaml
```
