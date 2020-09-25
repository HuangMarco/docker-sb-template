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

### 在pom.xml中配置jib

```xml

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>

			<plugin>
				<groupId>com.google.cloud.tools</groupId>
				<artifactId>jib-maven-plugin</artifactId>
				<version>2.5.0</version>
				<configuration>
					<from>
						<image>anbclub/alpine-jdk:v01</image>
					</from>
					<to>
						<image>${image.path}</image>
					</to>
				</configuration>
			</plugin>
		</plugins>
	</build>
```

### 命令行创建image到docker daemon

```shell
export IMAGE_PATH=registry.hub.docker.com/anbclub/messaging
mvn compile com.google.cloud.tools:jib-maven-plugin:2.5.0:build -Dimage=$IMAGE_PATH
```

### 提交image

```shell
docker tag reponame:imageVersion remoteDockerhubRepo:imageVersion
```
