## OpenShift

This is a little cheatsheet about [OpenShift](https://www.openshift.com).

### Start OpenShift with previously data
```
oc cluster up --host-data-dir=openshift --host-config-dir=openshift --use-existing-config --logging=true --metrics=true
```

### Scale down app to zero pods or idle
````
for a in `oc get dc | awk -F' ' '{print $1}'`; do { oc scale --replicas=0 dc $a; }; done
for a in `oc get dc | awk -F' ' '{ print $1 }'`; do { oc idle $a; }; done
````

### Cluster adm
```
oc adm policy add-role-to-user cluster-admin anderson.feitosa

oc adm policy add-cluster-role-to-user cluster-admin anderson.feitosa

oc policy add-role-to-user system:image-puller system:serviceaccount:sippe-service-registry:default -n sippe
```

### Get info from internal Docker Registry
```
oc get svc docker-registry -n default
```

### Login on internal Docker Registry
```
docker login -u anderson.feitosa -p uNhqwMlmWpDgWz8GC8AH6d0Fr2brzVWwhBMsgxO_BmA https://docker-registry-default.pocose.cabal.com.br
```

#### Get all resources with a label
```
oc get all -l app=service-registry
```

#### Delete all resources with a label
```
oc delete all -l app=service-registry
```

