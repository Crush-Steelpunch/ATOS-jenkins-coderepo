# ATOS-jenkins-coderepo
Example Code Repo for Atos delivery

Launch instance
- Compute Engine
  - set name to: yourinitials-jenkins
  - Set Region
  - type: e2-small
  - Network tags: jenkins
  - boot disk: Ubunti 20.04 LTS

Open SSH in Browser

```bash
nano installjenkins
chmod +x installjenkins
sudo ./installjenkins
```


Browse to `http://<your-external-ip>:8080`

Finish the set up using the browser.


# JDK 17 with Maven 3.8.5

Install jdk 17 and jre 8

```
sudo apt install -y openjdk-17-jdk openjdk-8-jre
```


Overwrite the jenkins service file to use jre8

```
sudo curl -L -o /etc/systemd/system/jenkins.service https://github.com/Crush-Steelpunch/ATOS-jenkins-coderepo/raw/main/jenkins.service
sudo systemctl daemon-reload
```

Install maven 3.8.5

```
curl -L -o /tmp/apache-maven-3.8.5-bin.tar.gz  https://dlcdn.apache.org/maven/maven-3/3.8.5/binaries/apache-maven-3.8.5-bin.tar.gz
sudo tar xf /tmp/apache-maven-*.tar.gz -C /opt
sudo ln -s /opt/apache-maven-3.8.5 /opt/maven
```

In the main dashboard navigate to **Manage Jenkins** > **Global Tool Configuration**

Scroll down to Maven Installations and click the button

Set a name for the installation

Untick the box **Install Automatically**

Set `MAVEN_HOME` directory to `/opt/maven`
