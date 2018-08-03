## POM.XML

Note simple maven build file example

    <project 
    xmlns="http://maven.apache.org/POM/4.0.0" 
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd"
    >
        <modelVersion>4.0.0</modelVersion>

        <groupId>de.codeboje.springbootbook</groupId>
        <artifactId>spam-detection</artifactId>
        <version>1.0.0-SNAPSHOT</version>

        <name>Spring Boot Book - Spam Detection</name>

        <dependencies>
            <dependency>
                <groupId>junit</groupId>
                <artifactId>junit</artifactId>
                <version>4.12</version>
                <scope>test</scope>
            </dependency>
        </dependencies>
    </project>

## Directory Structure

Source code root directory is always src/main/java.

## Compile program

    mvn package

## Run the class with the main() method

    java -cp target/{artifact} {NameOfClassWithMain} {Arguments}
    java -cp target/spam-detection-1.0.0-SNAPSHOT.jar SpamCheckerApplication viagra