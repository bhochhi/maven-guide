https://maven.apache.org/pom.html#Dependencies
https://maven.apache.org/guides/mini/guide-multiple-modules.html

###[When to us Aggregation(or Multi-Module) Maven project](https://maven.apache.org/guides/mini/guide-multiple-modules.html)

* An aggregate project will have multiple modules.
* An aggregate project has __pom__ as packaging type. 
* Each modules is a maven project and they are listed as relative directory using \<module\> tag in aggregate project.
```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
                      https://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
 
  <groupId>org.codehaus.mojo</groupId>
  <artifactId>my-aggregate-project</artifactId>
  <version>1.0</version>
  <packaging>pom</packaging>
 
  <modules>
    <module>first-project</module>
    <module>second-project</module>
  </modules>
</project>
```
* 

###[What is transitive dependencies?]()

###[Maven depenency Managements]()

###[Maven life cycles and goals]()

###[Understanding Maven]()
