# docker-sb-template
The template for dockerized sb application.

## Update credentials in maven settings

```xml
<server>
    <id>registry.hub.docker.com</id>
    <username>archnbclub</username>
    <password><![CDATA[your-password]]></password>
</server>
```

## Update jib image settings

```xml
https://github.com/GoogleContainerTools/jib/tree/master/jib-maven-plugin#example
```

## Use Jib

```shell
export IMAGE_PATH=registry.hub.docker.com/anbclub/messaging
mvn compile com.google.cloud.tools:jib-maven-plugin:2.5.0:build -Dimage=$IMAGE_PATH
```
