## RH SSO

This is a little cheatsheet about [RH SSO](https://access.redhat.com/products/red-hat-single-sign-on).

### Running Keycloak
```
docker run --name mykeycloak -p 8080:8080 -e KEYCLOAK_ADMIN=admin -e KEYCLOAK_ADMIN_PASSWORD=admin quay.io/keycloak/keycloak:latest start-dev
```



### Change level log in RH SSO
```
oc login <https://loadbalancer.host.myexample.com:443> --token=<aBCDEyFGE0Kr0BR0B-I7vLHPX74RVIQoe-L0zesx3yZ>
oc project <proj-sso>
oc rsh <sso-1-pod>
/opt/eap/bin/jboss-cli.sh -c
[standalone@localhost:9990 /] /subsystem=logging/logger=org.keycloak/:add(category=org.keycloak,level=TRACE,use-parent-handlers=true)
{"outcome" => "success"}
```

### Recuperação de grupos do AD via RH SSO

```
export USERNAME=anderson.feitosa; export PASSWORD=123456

curl -s -k -d "client_id=svc-bitbucket" -d "client_secret=d5f6bbc4-a45d-44ae-a2cc-9a0fd91e44fa" -d "username=$USERNAME" -d "password=$PASSWORD" -d "grant_type=password" "https://autenticacao.com.br/auth/realms/my_realm/protocol/openid-connect/token" | jq -r '.access_token | split(".") | .[1] | @base64d | fromjson'
```

### Remoção de todos os usuários do RH SSO
```
###
# LOGIN
###
./kcadm.sh config credentials --server http://192.168.99.100:8080/auth --realm master --user admin

###
# CREATE USERS 
###
for i in $(seq 1 100000); do { ./kcadm.sh create users -r myrealm -s username=$(uuidgen) -s enabled=true -o --fields id,username; echo $i; }; done; 

###
# LIST ALL USERS
###
for x in $(./kcadm.sh get users -r myrealm|jq -r '.[].id'); do { ./kcadm.sh get users/$x -r myrealm; }; done

###
# DELETE ALL USERS
###
for x in $(./kcadm.sh get users --limit 1000 -r myrealm | jq -r '.[].id'); do { echo $x; ./kcadm.sh delete users/$x -r myrealm; }; done
```

