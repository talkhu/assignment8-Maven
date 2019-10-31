# git clone https://github.com/talkhu/assignment8-Maven 
# cd assignment8-Maven
# mvn archetype:generate -DgroupId=com.fsd -DartifactId=fsd -DarchetypeArtifactId=maven-archetype-quickstart -	   DarchetypeVersion=1.1
# add spring boot , jpa data, thymeleaf and MVC
# mvn compile
# mvn package
# mvn clean


## execute the jar

```
		<plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
                <version>1.3.1.RELEASE</version>
                <executions>
                    <execution>
                        <goals>
                            <goal>repackage</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
```
command

```
mvn install
```

## clean all the compiled class files and jar files in target folder?

`mvn clean`

## Change POM.xml to create war. Run the command to create .war executable.

`<packaging>war</packaging>`

command

`mvn clean package`

## Create manageruser in tomcat by creating the config entry in tomcat-users.xml

```
<role rolename="manager-gui"/>     
 <user username="manager" password="manager" roles="manager-gui"/>
```

## jetty

```
<!-- https://mvnrepository.com/artifact/org.eclipse.jetty/jetty-maven-plugin -->
<dependency>
    <groupId>org.eclipse.jetty</groupId>
    <artifactId>jetty-maven-plugin</artifactId>
    <version>9.4.21.v20190926</version>
</dependency>
```



# GIT Assignment
```
1. Create a new maven project with default archetype.

`mvn archetype:generate`

2. Compile the project and generate jar/war file for the project using maven at command prompt.

`mvn clean package`

3. Initialize the newly created project as a GIT repository
github page , create repository
4. Commit the repository to the internal GIT server
5. Currently all files are committed to remote repository. Configure the local repository such that target folder is not committed from local repository to remote repository.
New a file .gitignore file, write a line:  target/
6. Delete the “target” folder from the remote repository which was committed in step 4.
 Delete file, then commit, then push

```
git commit -m “delete file”
git push origin
```

7.
Create a new branch “welcome api” in the local repository.
a.	Make changes to the source code i.e. add a new url (/welcome) to the rest controller

```
git branch welcomeapi
git checkout welcomeapi
```
b.	Now, push the change from local repository to remote repository in the branch “welcomeapi”

```
git commit -a –m “commit to breach welcomeapi”
```
c. You must not push these changes to main branch in remote repository.
d. Locally, merge the changes done welcomeapi branch to main branch. 

```
git checkout master
git merger welcomeapi
```
e. Push the changes from local repository to remote repository.
f. Once the changes are merged and pushed to the remote copy of repository on GIT 
server, delete the branch welcomeapi.

```
git branch -d welcomeapi
```

