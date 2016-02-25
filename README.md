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
*  A machanism how maven handles the multi modules project is call __reactor__, It collects, sorts and builds various modules.

That's brief about that multi modules project is. When to use such structure? When you want to decouple your section of codes that can reusable into multiple projects, you want to compartmentalize into single-alone components. That's when you creating multi modules project makes sense. But can't you acheive such goals by just creating separte projects and referencing as a parent POM? Yes you could but some other benefits could be 
  * you don't have to build each projects separately, or even resolve the dependencies. Reactor handles that for you. You can have just one command to do all builds. 
  * Another good benefit I see if your deployment strategy. You may have seperate webapps as the modules and they both could depends on various modules. If you need to create the deploy such webapps seperately into various servers, you can simple create all those profiles into aggregate project so that your strategies are on same file.
  
Finally checkout the example multi modules project in my [repo]()

###[what are plugins? How to build one?]()

###[Understand various elements of POM](https://maven.apache.org/pom.html)

###[What is transitive dependencies?]()

###[Maven depenency Managements]()

###[Maven life cycles and goals]()

###[Understanding Maven]()
