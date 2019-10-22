# Orbeon 

Orbeon for tomcat deployment enabled with keycloak.

## Installation

Create a war file and place it in tomcat webapps folder


## Customaization

in WEB-INF/keycloak.json update auth-server-ur, realm, resource etc,.

```
{
  "realm": "orbeonRealm",
  "auth-server-url": "http://localhost:9000/auth",
  "ssl-required": "external",
  "resource": "test­app",
  "public-client": true,
  "confidential-port": 0
}
```

## Forms

We can use keycloak user role in forms to control the visibility of the field

```
<xf:bind id="control-4-bind" ref="control-4" name="control-4" xxf:whitespace="trim"
                             relevant="fr:user-roles() = 'role0'"/>
```

Refer WEB-INF\resources\config\properties-local.xml for calling a REST api upon button click, pre-populating data on new form and custom button name.

## Url's

below is the URL to access form data in H2 Database

```
http://localhost:8080/orbeon/exist/rest/db/orbeon/fr/test/testForm/data
http://localhost:8080/orbeon/exist/rest/db/orbeon/fr/test/testForm/data/afc8e72d40ff5fa6d35631968b3b703538416e83/data.xml
```

```
http://localhost:8080/orbeon/exist/rest/db/orbeon/fr/test/testForm/data
http://localhost:8080/orbeon/exist/rest/db/orbeon/fr/test/testForm/data/afc8e72d40ff5fa6d35631968b3b703538416e83/data.xml
http://localhost:8080/orbeon/fr/test/testForm/new
```
