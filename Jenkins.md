# Jenkins Tool

## Jenkins is a CICD tool
-  you can install this on windows/Linux/mac
-  it requires java as it is developed with Java
-  follow this https://www.jenkins.io/doc/book/installing/linux/#debianubuntu
  ```sh
sudo apt update
sudo apt install fontconfig openjdk-21-jre
java -version
```
- [ ] Now Install jenkins
```sh
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt update
sudo apt install jenkins
```

- jenkins database stored at this location `/var/lib/jenkins`

------------------------
## Task 01
- [ ] Create 5 jobs in Jenkins
- [ ] Explore settings
- [ ] Integrate with Kubernetes
- [ ] Student project jobs
- [ ] Create Jenkins Agents

## Task 02
- [ ] Deploy Student App on kuberntes
- [ ] Deploy student App using CICD pipeline
    - [ ] create a build
    - [ ] Create an image
    - [ ] push image to dockerhub
    - [ ] Deploy from dockerhub image
  
