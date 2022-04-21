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

Installing maven and the jdk on the cli so you can use the maven jenkins plugin

```bash
sudo apt install -y maven default-jdk
```

In the main dashboard navigate to **Manage Jenkins** > **Global Tool Configuration**

Scroll down to Maven Installations and click the button

Set a name for the installation

Untick the box **Install Automatically**

Set `MAVE_HOME` directory to `/usr/share/maven`
