创建java项目代码

mvn archetype:generate -DgroupId=com.hand  -DartifactId=myPro  -DarchetypeArtifactId=maven-archetype-quickstart  -DinteractiveMode=false -DarchetypeCatalog=local

编译java文件

mvn clean compile

运行.class文件

mvn exec:java -Dexec.mainClass="com.hand.App" -Dexec.args="arg0 arg1 arg2"



------------------------------------------------------------------------------------------

创建web项目
mvn archetype:generate -DgroupId=com.hand -DartifactId=myWeb -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false  -DarchetypeCatalog=local

更改pom.xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.hand</groupId>
  <artifactId>webtest</artifactId>
  <packaging>war</packaging>
  <version>1.0-SNAPSHOT</version>
  <name>webtest Maven Webapp</name>
  <url>http://maven.apache.org</url>
  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>3.8.1</version>
      <scope>test</scope>
    </dependency>
  </dependencies>
  <build>
    <finalName>webtest</finalName>
    <plugins>
      <plugin>
                <groupId>org.eclipse.jetty</groupId>
                <artifactId>jetty-maven-plugin</artifactId>
                <version>9.2.11.v20150529</version>
                <configuration>
                    <webAppConfig>
                        <allowDuplicateFragmentNames>true</allowDuplicateFragmentNames>
                    </webAppConfig>
                </configuration>
            </plugin>
    </plugins>
  </build>
</project>

运行
mvn jetty:run

在网页中打开
localhost:8080