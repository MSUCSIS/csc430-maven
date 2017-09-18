# Maven
Repository for storing maven artifacts.

## Using in projects
For a given project, you will want to use the blob-api code for the given version to program against. To add this to your projects, you will need to modify your *pom.xml* file as described below:

### Add New Maven Repository

You will need to add the following to your *pom.xml* file so that Maven will know to search this repository for artifacts:

    <repositories>
        <repository>
            <id>BlobAPI-mvn-repo</id>
            <url>https://raw.github.com/MSUCSIS/csc430-maven/mvn-repo/</url>
            <snapshots>
                <enabled>true</enabled>
                <updatePolicy>always</updatePolicy>
            </snapshots>
        </repository>
    </repositories>

Once you have added this repository, you must add a dependency on the blob-api artifact itself.

### Add Maven Dependency

In the *dependencies* section of your *pom.xml* file, you will need to add the following:

    <dependency>
        <groupId>edu.murraystate.csc430</groupId>
        <artifactId>blob-api</artifactId>
        <version>1.0</version>
    </dependency>
    
This tells Maven that your code will not compile and execute properly without the code in the *blob-api.jar* artifact. 
Accordingly, Maven will search the repository we added above (as well as some other built-in default repositories) 
until it finds version *1.0* of the file *blob-api.jar*. It will then download this file and add it to your classpath 
as necessary when compiling, executing, etc. 
