# Marine POS Cluster Config

## Access Cluster

Windows 
```shell
$ SET KUBECONFIG=C:\Users\TOE\.kube\marine-sml-cluster-kubeconfig.yaml
```

Mac
```shell
$ export KUBECONFIG=/Users/toe/.kube/marine-sml-cluster-kubeconfig.yaml
```


Or
```
 kubectl get nodes --kubeconfig=C:\Users\TOE\.kube\sml-uat-kubeconfig.yaml
```


export KUBECONFIG=/Users/toe/.kube/sml-uat-kubeconfig.yaml


test redis

```
   echo -e "*1\r\n$4\r\nPING\r\n" | nc <redis_host> <redis_port>


   echo -e "*2\r\n$4\r\nAUTH\r\n$32vaJrat-1hazdi-surfod\r\n*1\r\n$4\r\nPING\r\n" | nc <redis_host> <redis_port>

```


Example Ingress

```yaml
# Please edit the object below. Lines beginning with a '#' will be ignored,
# and an empty file will abort the edit. If an error occurs while saving this file will be
# reopened with the relevant failures.
#
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  annotations:
    kubectl.kubernetes.io/last-applied-configuration: |
      {"apiVersion":"networking.k8s.io/v1","kind":"Ingress","metadata":{"annotations":{},"name":"ingress-product-dealer-api-uat","namespace":"sml-uat"},"spec":{"ingressClassName":"nginx","rules":[{"host":"dealer-api-sml-uat.dohome.co.th","http":{"paths":[{"backend":{"service":{"name":"service-product-dealer-api-uat","port":{"number":8080}}},"path":"/healthz","pathType":"Prefix","property":{"ingress.beta.kubernetes.io/url-match-mode":"STARTS_WITH"}},{"backend":{"service":{"name":"service-product-dealer-api-uat","port":{"number":8080}}},"path":"/productdealerapi/v1/","pathType":"Prefix","property":{"ingress.beta.kubernetes.io/url-match-mode":"STARTS_WITH"}}]}}],"tls":[{"hosts":["dealer-api-sml-uat.dohome.co.th"],"secretName":"dohome-secret"}]},"status":{"loadBalancer":{"ingress":[{"ip":"10.210.103.194"},{"ip":"159.138.238.187"}]}}}
  creationTimestamp: "2023-09-13T09:20:20Z"
  generation: 8
  name: ingress-product-dealer-api-uat
  namespace: sml-uat
  resourceVersion: "148869153"
  uid: 044b4982-9c40-4f31-99c6-7fb0276a4584
spec:
  ingressClassName: nginx
  rules:
  - host: dealer-api-sml-uat.dohome.co.th
    http:
      paths:
      - backend:
          service:
            name: service-product-dealer-api-uat
            port:
              number: 8080
        path: /healthz
        pathType: Prefix
        property:
          ingress.beta.kubernetes.io/url-match-mode: STARTS_WITH
      - backend:
          service:
            name: service-product-dealer-api-uat
            port:
              number: 8080
        path: /productdealerapi/v1/
        pathType: Prefix
        property:
          ingress.beta.kubernetes.io/url-match-mode: STARTS_WITH
  tls:
  - hosts:
    - dealer-api-sml-uat.dohome.co.th
    secretName: dohome-secret
status:
  loadBalancer:
    ingress:
    - ip: 10.210.103.194
    - ip: 159.138.238.187
```


```yaml
# Please edit the object below. Lines beginning with a '#' will be ignored,
# and an empty file will abort the edit. If an error occurs while saving this file will be
# reopened with the relevant failures.
#
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  annotations:
    kubectl.kubernetes.io/last-applied-configuration: |
      {"apiVersion":"networking.k8s.io/v1","kind":"Ingress","metadata":{"annotations":{},"name":"sml-marine-center-api-uat","namespace":"sml-uat"},"spec":{"ingressClassName":"nginx","rules":[{"host":"dealer-api-sml-uat.dohome.co.th","http":{"paths":[{"backend":{"service":{"name":"sml-marine-center-api-uat","port":{"number":8080}}},"path":"/smlmarinecenter/api/v1/","pathType":"Prefix","property":{"ingress.beta.kubernetes.io/url-match-mode":"STARTS_WITH"}}]}}],"tls":[{"hosts":["dealer-api-sml-uat.dohome.co.th"],"secretName":"dohome-secret"}]},"status":{"loadBalancer":{"ingress":[{"ip":"10.210.103.194"},{"ip":"159.138.238.187"}]}}}
  creationTimestamp: "2025-01-16T02:32:45Z"
  generation: 1
  name: sml-marine-center-api-uat
  namespace: sml-uat
  resourceVersion: "200904969"
  uid: 551f16f2-febe-4947-bc9e-a6afd1ac2ac5
spec:
  ingressClassName: nginx
  rules:
  - host: dealer-api-sml-uat.dohome.co.th
    http:
      paths:
      - backend:
          service:
            name: sml-marine-center-api-uat
            port:
              number: 8080
        path: /smlmarinecenter/api/v1/
        pathType: Prefix
        property:
          ingress.beta.kubernetes.io/url-match-mode: STARTS_WITH
  tls:
  - hosts:
    - dealer-api-sml-uat.dohome.co.th
    secretName: dohome-secret
status:
  loadBalancer:
    ingress:
    - ip: 10.210.103.194
    - ip: 159.138.238.187

```