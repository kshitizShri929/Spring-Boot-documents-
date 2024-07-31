# Custom Archetype Creation from an Existing Project in Spring Boot Framework
## Project: Spring Boot Employee CRUD System

This Spring Boot application manages employee data by allowing users to perform CRUD operations: create, read, update, and delete employee records without using a database.


### SYSTEM DETAILS

- OS:   PRETTY_NAME="Ubuntu 22.04.4 LTS"
  
      NAME="Ubuntu"

      VERSION_ID="22.04"

      VERSION="22.04.4 LTS (Jammy Jellyfish)"

      VERSION_CODENAME=jammy

      ID=ubuntu

      ID_LIKE=debian

      HOME_URL="https://www.ubuntu.com/"

      SUPPORT_URL="https://help.ubuntu.com/"

      BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"

      PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"

      UBUNTU_CODENAME=jammy

- Java: 
openjdk version "17.0.11"
- Maven
Apache Maven 3.9.4 
- Springboot 2.5.2

- IDE  vscode 1.87.0

# There are a few steps we follow for creating a custom archetype and reusing it for generating new projects.

## Step 1: Clone the Existing Project 
Open your terminal and run the following command to clone the existing Spring Boot project from GitHub:

For Example-
```bash

git clone https://github.com/prashanthbilla/CRUD-SpringBoot-without-DataBase.git
```
*you can also replace this with other project github repostory

**git clone-** This command is used to create a copy of a remote repository on your local machine.
### OUTPUT:

```
sk@sk:~/NoidaOffice$ git clone https://github.com/prashanthbilla/CRUD-SpringBoot-without-DataBase.git
Cloning into 'CRUD-SpringBoot-without-DataBase'...
remote: Enumerating objects: 393, done.
remote: Counting objects: 100% (50/50), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 393 (delta 48), reused 47 (delta 47), pack-reused 343
Receiving objects: 100% (393/393), 52.22 KiB | 668.00 KiB/s, done.
Resolving deltas: 100% (155/155), done.
open project on vscode   

sk@sk:~/NoidaOffice$ 
```

## Step 2: Open the Project in Your IDE
Navigate to the project directory and open it in your preferred IDE (e.g., Visual Studio Code):

For example :
```bash

cd CRUD-SpringBoot-without-DataBase/
code .
```

*you can move actual project directory and this anyother IDE

 ## Step 3: Run the Spring Boot Application

To ensure that the project is working correctly, you can run the Spring Boot application with the following command:

```bash

mvn spring-boot:run
```
**mvn-** This command is used to execute Maven, a tool that automates the building, testing, and management of Java projects.

**spring-boot-** This indicates the Spring Boot plugin, which is specifically designed to facilitate the development and management of Spring Boot applications.

**run-** This is the goal that tells Maven to start your Spring Boot application.
### OUTPUT:
```
sk@sk:~/NoidaOffice/CRUD-SpringBoot-without-DataBase$ mvn spring-boot:run
[INFO] Scanning for projects...
[INFO] 
[INFO] --------------------------< com.example:demo >--------------------------

[INFO] <<< spring-boot:2.5.2:run (default-cli) < test-compile @ demo <<<
[INFO] 
[INFO] 
[INFO] --- spring-boot:2.5.2:run (default-cli) @ demo ---
[INFO] Attaching agents: []

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.5.2)


2024-07-31 11:15:10.850  INFO 19202 --- [  restartedMain] c.e.demo.SpringCrudWithoutDbApplication  : Started SpringCrudWithoutDbApplication in 2.086 seconds (JVM running for 2.783)

```
after verifying project correctly working  then we move next step 
## Step 4: Create the Archetype from the Project

 We will create an archetype from the existing project. Run the following command:

```bash
 
mvn archetype:create-from-project

```
This command generates a Maven archetype from the current project, allowing you to create a reusable template that can be used to generate new projects with the same structure and configuration.

OUTPUT:

```
sk@sk:~/NoidaOffice/CRUD-SpringBoot-without-DataBase$ mvn archetype:create-from-project
[INFO] Scanning for projects...
[INFO] 
[INFO] --------------------------< com.example:demo >--------------------------
[INFO] Building Spring Crud without DB 0.0.1-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  1.377 s
[INFO] Finished at: 2024-07-31T11:24:49+05:30
[INFO] ------------------------------------------------------------------------
[INFO] Archetype project created in /home/sk/NoidaOffice/CRUD-SpringBoot-without-DataBase/target/generated-sources/archetype
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  5.484 s
[INFO] Finished at: 2024-07-31T11:24:49+05:30
[INFO] ------------------------------------------------------------------------
sk@sk:~/NoidaOffice/CRUD-SpringBoot-without-DataBase$ 

```
This command will generate the archetype in the target/generated-sources/archetype directory.

## Step 5: Navigate to the Generated Sources
Go to the generated sources directory:

```bash

cd target/generated-sources/archetype/

```

Now, install the archetype using the following command:

```bash
mvn clean install
```
**mvn clean install-** This command is a widely used Maven command that accomplishes two key tasks:

**clean:** Deletes the target directory, which holds compiled files and artifacts from prior builds, ensuring a clean build environment.

**install:** Compiles the project, runs tests, packages the application, and installs the resulting artifact (such as a JAR or WAR file) into the local Maven repository for use in other projects.






### OUTPUT:
```
sk@sk:~/NoidaOffice/CRUD-SpringBoot-without-DataBase/target/generated-sources/archetype$ mvn clean install
[INFO] Scanning for projects...
[INFO] 
[INFO] ---------------------< com.example:demo-archetype >---------------------
[INFO] Building demo-archetype 0.0.1-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------[ maven-archetype ]---------------------------

[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  1.518 s
[INFO] Finished at: 2024-07-31T11:37:06+05:30
[INFO] ------------------------------------------------------------------------
sk@sk:~/NoidaOffice/CRUD-SpringBoot-without-DataBase/target/generated-sources/archetype$ 

```
## Step 6: Generate a New Project from the Archetype
To generate a new project using the custom archetype, go back to your home directory ( or any directory  you want where  not pom) and run:

```bash

cd ~/NoidaOffice
mvn archetype:generate
```
**mvn archetype:generate-** This command is used in Maven to create a new project based on a specified archetype.


During this process:

You may need to find the local directory PID and enter it.
Follow the prompts and enter Y to confirm.
### OUTPUT:

```
.
.
.
3450: local -> com.example:student-crud-archetype (student-crud-archetype)
3451: local -> org.acme:rest-client-reactive-quickstart-archetype (rest-client-reactive-quickstart-archetype)
3452: local -> com.example:demo-archetype (Demo project for Spring Boot)
3453: local -> br.com.darchanjo.examples:spring-boot-crud-rest-archetype (Sample project implementing a CRUD application with Spring Boot)
Choose a number or apply filter (format: [groupId:]artifactId, case sensitive contains): 2158: 3452
Define value for property 'groupId': com.example
Define value for property 'artifactId': demo
Define value for property 'version' 1.0-SNAPSHOT: : 1.0-SNAPSHOT
Define value for property 'package' com.example: : com.example
Confirm properties configuration:
groupId: com.example
artifactId: demo
version: 1.0-SNAPSHOT
package: com.example
 Y: : y
[INFO] ----------------------------------------------------------------------------
[INFO] Using following parameters for creating project from Archetype: demo-archetype:0.0.1-SNAPSHOT
[INFO] ----------------------------------------------------------------------------
[INFO] Parameter: groupId, Value: com.example
[INFO] Parameter: artifactId, Value: demo
[INFO] Parameter: version, Value: 1.0-SNAPSHOT
[INFO] Parameter: package, Value: com.example
[INFO] Parameter: packageInPathFormat, Value: com/example
[INFO] Parameter: package, Value: com.example
[INFO] Parameter: groupId, Value: com.example
[INFO] Parameter: artifactId, Value: demo
[INFO] Parameter: version, Value: 1.0-SNAPSHOT
[INFO] Project created from Archetype in dir: /home/sk/NoidaOffice/demo
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  01:37 min
[INFO] Finished at: 2024-07-31T12:43:30+05:30
[INFO] ------------------------------------------------------------------------
sk@sk:~/NoidaOffice$ 
```
## Step 7: Run the New Project
Once the new project is generated, navigate to the new project directory and run the Spring Boot application using:

```bash

mvn spring-boot:run

```
### OUTPUT:
```sk@sk:~/NoidaOffice/demo$ mvn spring-boot:run
[INFO] Scanning for projects...

[INFO] --- spring-boot:2.5.2:run (default-cli) @ demo ---
[INFO] Attaching agents: []

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.5.2)


[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  01:25 h
[INFO] Finished at: 2024-07-31T14:10:11+05:30
[INFO] ------------------------------------------------------------------------
sk@sk:~/NoidaOffice/demo$ 
```

## Conclusion

We have successfully created a custom Maven archetype from an existing Spring Boot project and generated a new project using that archetype. This process allows you to reuse code and structure for similar projects efficiently.


#### NOTE : 
Perform CRUD operations on employee details at: http://localhost:8080/employees.

## Reference:
  - Project- https://github.com/prashanthbilla/CRUD-SpringBoot-without-DataBase

- Maven Archetype Guide https://maven.apache.org/guides/mini/ guide-creating-archetypes.html
- Video Tutorials- https://www.youtube.com/watch?v=U3AvNVT5j8w




