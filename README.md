# Gatling

Gatling is a load testing tool that comes with support of the HTTP protocol –
which makes it a really good choice for load testing any HTTP server.

## Pre requisite:
1. Install Scala plugin into Intelij

## Creating a project using Gatling's Maven Archetype

1. Execute the following command in terminal:
```
  mvn archetype:generate
```

2. When prompted to choose a number or filter, enter:
```
  gatling
```

3. Select the archetype:
```
  io.gatling.highcharts:gatling-highcharts-maven-archetype (gatling-highcharts-maven-archetype)
```  
4. Then when prompted to select the version, choose the latest version.

5. Enter a groupId, artifactId, version and package for the archetype and confirm the same.

6. Finish by importing the archetype into an IDE

## Configure a Recorder

Run the Recorder class from IDE. It will launch the Recorder GUI. Once it is launched, configure how requests and responses will be recorded in the GUI. Choose the following options:

1. 8000 as listening port
2. Follow Redirects? checked
3. Automatic Referers? checked
4. Black list first filter strategy selected
5. .*\.css, .*\.js and .*\.ico in the black list filters

## Record the scenario

## Run the simulation with Maven
To run the recorded simulation, add this to pom.xml:
```
<plugin>
    <groupId>io.gatling</groupId>
    <artifactId>gatling-maven-plugin</artifactId>
    <version>2.2.4</version>
    <executions>
        <execution>
            <phase>test</phase>
            <goals><goal>execute</goal></goals>
            <configuration> 
                <disableCompiler>true</disableCompiler> 
            </configuration>
        </execution>
    </executions>
</plugin>
```

Execute the following command in terminal:
```
  mvn test
```

## Result

Open the index.html file
