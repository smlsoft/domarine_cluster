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
```