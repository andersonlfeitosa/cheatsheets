## RH SSO

This is a little cheatsheet about [RH SSO](https://access.redhat.com/products/red-hat-single-sign-on).

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
