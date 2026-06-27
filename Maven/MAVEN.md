<h1>MAVEN</h1><br>
Maven is a build tool.<br>
<h2>Understanding Java Applications: </h2><br>
Java source code is compiled into byte code (".class" file).<br>
To execute any testcases available, we run them through JUnit5. <br>
To deploy this source code as a Java application, the source code is packaged into .jar/.war build files.<br>
Building is the process of translating human readable source code into a packaged, executable format that a server or device can actually run.<br>

Maven is a tool that automates this build process, before deploying.<br>

If there are any libraries or frameworks being used in the application, the jar or war files do not have them defined. To do this, you might have to install the jar or war files from the browser of those libraries and integrate them into the IDE's build process. This means, you have to run the testcases again manually. These libraries, frameworks or modules the application is dependent on, are called dependencies.<br>
<br>
<h2>What does Maven do?</h2><br>
1. It creates the standard project folder structure.<br>
2. It downloads and manages dependencies automatically.<br>
3. Executes unit testcases using testing frameworks like JUnit5.<br>
<h2>Creating a new Maven Project:</h2><br>
Command: mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.5 -DgroupId=com.mycompany.app -DartifactId=my-new-project<br>

1. mvn: invokes Maven command line.<br>
2. -D: define command. <br>
3. archetype:generate : Generates a template that needs to be created by Maven.<br>
4. -DarchetypeGroupId=org.apache.maven.archetypes : Company or organization under which the project is being created.<br>
5. -DarchetypeArtifactId=maven-archetype-quickstart : It specifies the project name. A standalone project.<br>
6. -DarchetypeVersion=1.5 : The version of the project that's being used.<br>
7. -DgroupId=com.mycompany.app : Project's group ID (more like the team that's handling it currently).<br>
8. -DartifactId=my-new-project : Project folder. Jar or war files are created under this name.<br>
9. -DinteractiveMode = false indicates that there is no need of sending any parameters and true indicates that you need to pass parameters when you run the project.<br>

groupId vs artifactId : group ID says who's doing it and artifact ID says what it is doing.<br>