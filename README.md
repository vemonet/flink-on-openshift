Written from the [official Flink Kubernetes documentation](https://ci.apache.org/projects/flink/flink-docs-stable/ops/deployment/kubernetes.html). Images built from [apache/flink](https://github.com/apache/flink).

A mount to a PVC storage has been add on `/mnt` (inside the pod). 

⚠️ **Change the PVC name in  before creating the deployment** in files:

* jobmanager-deployment.yaml
* taskmanager-deployment.yaml

Script to deploy Flink Job and Task managers in the current project. 

```bash
oc project my-project
./create_deployment.sh
```

> Flink home folder inside the pod is `/opt/flink`

> PVC shared in `/mnt`

Details of commands:

```bash
oc create -f flink-configuration-configmap.yaml
oc create -f jobmanager-service.yaml
oc create -f jobmanager-deployment.yaml
oc create -f taskmanager-deployment.yaml
oc create -f jobmanager-rest-service.yaml
```
