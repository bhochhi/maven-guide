http://books.sonatype.com/mvnex-book/reference/multimodule.html

http://books.sonatype.com/mvnex-book/reference/customizing.html

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
  * Another good benefit I see is with your deployment strategy where you want to release all your webapps/webservices simultaneously where you can have one command. However this may sounds little inconvicing because why would someone want to deploy app1 and when they just need to deploy app2 while app1 and app2 directly doesn't depend on each other. In such instance I would like them as standalone projects. However, you can still deploy the projects seperately by creating various profiles into aggregate project so that your strategies are on same file. But again this is not convincing as you have to update the whole repository and will be nightmare to mention the version of each apps independently. 

So, final words, know what your really want before you decide for multi-module project. and Check out my [repo]() for some demonstration.

###[what are plugins? How to build one?]
Plugins are collection of one or more goals. 

###[Understand various elements of POM](https://maven.apache.org/pom.html)

###[What is transitive dependencies?]()
When your project A depends on Project B but project B itself depends on Project C and D, We can project C and D a transitive dependencies of project A. With Maven, you just need to define Project B as your dependencies. Maven will be able to bring in C and D implicitly which will be needed for your project to compile. Things get little interesting when:
 
 1. A project depends on different version of project(different level dependencies, A and B different level). For instance, project A depends on project E ver 1.0 and Project B depends on E ver 2.0.
 2. Project C and D project(same lavel) depends different version of Project E.
 

###[Maven depenency Managements]()


###[Maven lifecycles and goals](https://github.com/bhochhi/maven-guide/wiki/Maven-lifecycle,-phases-and-goals)


###[Understanding Maven](https://github.com/bhochhi/maven-guide/wiki/Understanding-Maven)
