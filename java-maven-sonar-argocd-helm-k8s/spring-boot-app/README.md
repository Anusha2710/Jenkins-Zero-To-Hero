# Spring Boot based Java web application
 
This is a simple Sprint Boot based Java application that can be built using Maven. Sprint Boot dependencies are handled using the pom.xml 
at the root directory of the repository.

This is a MVC architecture based application where controller returns a page with title and message attributes to the view.

## Execute the application locally and access it using your browser

Checkout the repo and move to the directory

```
git clone https://github.com/iam-veeramalla/Jenkins-Zero-To-Hero/java-maven-sonar-argocd-helm-k8s/sprint-boot-app
cd java-maven-sonar-argocd-helm-k8s/sprint-boot-app
```

Execute the Maven targets to generate the artifacts

```
mvn clean package
```

The above maven target stroes the artifacts to the `target` directory. You can either execute the artifact on your local machine
(or) run it as a Docker container.

** Note: To avoid issues with local setup, Java versions and other dependencies, I would recommend the docker way. **


### Execute locally (Java 11 needed) and access the application on http://localhost:8080

```
java -jar target/spring-boot-web.jar
```

### The Docker way

Build the Docker Image

```
docker build -t ultimate-cicd-pipeline:v1 .
```

```
docker run -d -p 8010:8080 -t ultimate-cicd-pipeline:v1
```

Hurray !! Access the application on `http://<ip-address>:8010`


## Next Steps

### Configure a Sonar Server locally

```
- goto root user
sudo su -
-add sonarqube as user
adduser sonarqube
wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.4.0.54424.zip
unzip * - unzip not found
-go to root user and install unzip 
sudo su -
apt install unzip
-move to sonarqube user
unzip *
ls
chmod -R 755 /home/sonarqube/sonarqube-9.4.0.54424
chown -R sonarqube:sonarqube /home/sonarqube/sonarqube-9.4.0.54424
cd sonarqube-9.4.0.54424/bin/linux-x86-64/
./sonar.sh start
```

Hurray !! Now you can access the `SonarQube Server` on `http://<ip-address>:9000` 

### Generate Token in SonarQube

- Goto Sonarqube Server
- goto my account
- goto security
- generate token -jenkins
- copy token code

![image](https://github.com/Anusha2710/Jenkins-Zero-To-Hero/assets/47424821/859b5fbf-48fe-461e-b06f-c3d6ff707b91)

### Manage Credentials in Jenkins

-goto manage jenkins
- goto credetials
- click on system
- click on global credentials 
- add credentials
- create

![image](https://github.com/Anusha2710/Jenkins-Zero-To-Hero/assets/47424821/c54941f9-e2bf-42b6-a43c-94c35bae834f)
