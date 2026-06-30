<h1>MAVEN</h1>
Maven is a build tool.<br>
<h2>Understanding Java Applications: </h2>
Java source code is compiled into byte code (".class" file).<br>
To execute any testcases available, we run them through JUnit5. <br>
To deploy this source code as a Java application, the source code is packaged into .jar/.war build files.<br>
Building is the process of translating human readable source code into a packaged, executable format that a server or device can actually run.<br>

Maven is a tool that automates this build process, before deploying.<br>

If there are any libraries or frameworks being used in the application, the jar or war files do not have them defined. To do this, you might have to install the jar or war files from the browser of those libraries and integrate them into the IDE's build process. This means, you have to run the testcases again manually. These libraries, frameworks or modules the application is dependent on, are called dependencies.<br>
<h2>What does Maven do?</h2>
1. It creates the standard project folder structure.<br>
2. It downloads and manages dependencies automatically.<br>
3. Executes unit testcases using testing frameworks like JUnit5.<br>
<h2>Creating a new Maven Project:</h2>
Command: mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.5 -DgroupId=com.mycompany.app -DartifactId=my-new-project<br>

1. mvn: invokes Maven command line.<br>
2. -D: define command. <br>
3. archetype:generate : Generates a template that needs to be created by Maven. For example: maven-archetype-quickstart creates a standalone java application and maven-archetype-webapp creates a web application.<br>
4. version=1.5 : The version of the project that's being used.<br>
5. groupId=com.mycompany.app : Company or Organization name. It usually follows package naming syntax, using reverse domain name convention. Example: com.tcs<br>
6. artifactId=my-new-project : Project folder. Jar or war files are created under this name.<br>
7. interactiveMode = false indicates that there is no need of sending any parameters and true indicates that you need to pass parameters when you run the project.<br>
8. packagingType = jar: Specified if the project has to be packaged into jar file or war file. It packages into jar file by default if not specified.<br>
groupId vs artifactId : group ID says who's doing it and artifact ID says what it is doing.<br>
After running the command, a new Maven project is created and in the project, there is a file called pom.xml and a folder src. This file is how the project communicates with Maven. The tasks to be done by Maven are all specified in pom.xml.<br>
The src folder is where the source code of the application lies, the main and the testcases are defined, in the test.<br>
<h2>Important Terms:</h2>
<b>Maven Dependencies: </b>Libraries or external modules needed for project development like spring,hibernate,junit,kafka,redis,etc...<br>
<b>Maven Goals: </b>It is used to perform specific steps in Maven build lifecycle. For example: clean, compile, test, package, deploy.<br>
<b>Maven Repositories: </b>Storage location for Maven dependencies. It specifies where the dowloaded dependencies should be stored. There are 3 types of repositories: Central, remote and local. <br>
<h2>Maven Goals:</h2>
Syntax: mvn &lt;goal&gt;<br>
<b>compile: </b>On compiling the project, along with the src folder and pom.xml, we also have a new default output directory called target. All the outputs like the class files, test classes, jar or war files and many more are stored in target folder.<br>
<b>clean:</b> On using mvn clean command, the target folder is deleted i.e., the compiled files.<br>
Whenever a change is made to pom.xml, clean the target file and  compile the project again. If the target folder is not cleaned, a build error arises.<br>
<b>test: </b>On running test command, the project is both run adn tested.<br>
<b>package: </b>On running package command, the project is compiled, tested and packaged into a jar file.<br>
<b>clean package: </b>cleans the existing package and recompiles, executes testcases and packages it again.<br>
To package the project into jar or war file, it can be specified in packaging tag of pom.xml.<br>
<h2>Maven Dependencies:</h2>
External libraries or modules that the project needs in order to compile and run properly.
Example: spring-core, junit, hibernate, etc...<br>
Maven dependencies can be found on mvnrepository.com.<br>
These dependencies are added into the XML file as:
&lt;dependency&gt;<br>
    &lt;groupId&gt;  &lt;/groupId&gt;<br>
    &lt;artifactId&gt;  &lt;.artifactId&gt;<br>
    &lt;version&gt;  &lt;/version&gt;<br>
&lt;/dependency&gt;<br>
<h2>Maven Repositories: </h2>
There are 3 types of Maven Repositories. They are:<br>
1. Central Repository (Offlicial online repo) <br>
2. Local Repository (On local machine) <br>
3. Remote repository (Company or third party server) <br>
Dependencies are configured in pom.xml. When an application is being used, pom.xml checks for the dependency files in the local repository. If not found, it checks for the files in Central repository of Maven (repo.maven.apache.org) as jar/war files. This file is now added to the local repository and from there to the Maven application. <br>
Remote repository is a private repository maintained by an organization handling it's internal jar/war files. <br>
To add files from remote repo to the Maven application, they are first added to the local repo and then the application. <br>
Address of dependencies in local repository is: .m2/repository. All the dependencies are installed in this file. <br>
Note that mvnrepository.com is not a central repository. It is just a search engine that finds the JVM dependencies. <br>
packaging, name, url, modelVersion, groupId, artifactId and version of the project all together are called maven coordinates. <br>