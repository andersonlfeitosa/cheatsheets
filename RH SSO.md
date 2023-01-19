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