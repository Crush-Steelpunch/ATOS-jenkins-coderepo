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

# Maven and Jenkins

Install maven and the jdk on the ssh cli.

```bash
sudo apt install -y maven default-jdk
```

In the main dashboard navigate to **Manage Jenkins** > **Global Tool Configuration**

Scroll down to Maven Installations and click the button

Set a name for the installation

Untick the box **Install Automatically**

Set `MAVE_HOME` directory to `/usr/share/maven`

# JDK 17 with Maven 3.8.5

Install jdk 17

```
sudo apt install -y openjdk-17-jdk
```


Overwrite the jenkins service file to use jdk 8

```
sudo curl -L -o /etc/systemd/system/jenkins.service https://github.com/Crush-Steelpunch/ATOS-jenkins-coderepo/raw/main/jenkins.service
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

Set `MAVE_HOME` directory to `/opt/maven`
