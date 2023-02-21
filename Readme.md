# Guacamole

Guacamole is an HTML5 web application that provides access to desktop environments using remote desktop protocols (such as VNC or RDP). Guacamole is also the project that produces this web application, and provides an API that drives it. This API can be used to power other similar applications or services.

## Sources
* https://guacamole.apache.org/doc/gug/introduction.html
* https://github.com/MaxWaldorf/guacamole

## Install with Argo CD

Use a central repository which links to all Apps which has to be deployed,
and add the App desciption there, or deploy the App for Uptime Kuma manually.
Find a sample in my [App of Apps Repo](https://github.com/wep4you/k8s-apps.git),
there is also a sample definition for [Guacamole](https://github.com/wep4you/k8s-apps/blob/main/local/guacamole.yml)

## Install manual with kubectl

To add your own configuration, copy ```overlays/local``` to a new folder and change the files to your needs.
It's standard Kustomize format you can use.

    ```
    kubectl apply -k overlays/local
    ```

## Configure Extensions

Add extensions to the Evnironment Variable which is defined in the configmap.yml, either
with overriding it in your own overlay or patch it with kustomize. Find possible Extensions
in the following list, but be aware that you correctly configure them also in the configmap,
in the guacamole.properties section. Find more on the official [guacamole documentation](https://guacamole.apache.org/doc/1.4.0/gug/configuring-guacamole.html#guacamole-properties)

### Extension List:
auth-duo
auth-header
auth-jdbc-mysql
auth-jdbc-postgresql
auth-jdbc-sqlserver
auth-json
auth-ldap
auth-quickconnect
auth-sso-openid
auth-sso-saml
auth-sso-cas
auth-totp