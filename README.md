# CI/CD Pipeline Using Jenkins and GitHub Webhooks

## Overview

This project demonstrates a complete CI/CD pipeline built using Jenkins. The pipeline automates the process of cloning source code, testing it, building it into deployable artifacts, and finally deploying it to the target environment.

## Source Code Repository

This pipeline uses the following GitHub repository as the source:

**Repository:** [https://github.com/KishanGollamudi/Java-Web-Calculator-App.git](https://github.com/KishanGollamudi/Java-Web-Calculator-App.git)

## Pipeline Stages

1. **Cloning Job**

   * Fetches the latest code from GitHub.

2. **Test Job**

   * Executes automated tests to verify the integrity and functionality of the code.

3. **Build Job**

   * Builds the project and creates the output artifacts.

4. **Deploy Job**

   * Deploys the final build to the target server/environment.

## Jenkins Installation Script

The following script was used to install Jenkins on an Ubuntu server:

```bash
#!/bin/bash

sudo apt update
sudo apt install fontconfig openjdk-21-jre -y

sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt update
sudo apt install jenkins

echo "---------------------------Jenkins has been installed ------------------------"
```

## Jenkins Setup Steps

1. Installed Jenkins using a `script.sh` file.
2. Accessed Jenkins via `http://<server-ip>:8080`.
3. Retrieved Jenkins initial admin password from the system path.
4. Created admin credentials for Jenkins dashboard usage.
5. Created the four jobs listed above.
6. Installed the following plugins:

   * Build Pipeline Plugin
   * GitHub Plugin
   * GitHub Webhook Plugin
7. Configured pipeline view to visualize and trigger jobs sequentially.

## GitHub Webhook Integration

* Configured a webhook in GitHub to notify Jenkins upon every code push.
* Jenkins automatically triggered the pipeline when changes were pushed.

## Pipeline Flow

```
GitHub Commit → Clone Job → Test Job → Build Job → Deploy Job
```

## Screenshots Placeholder

> **Add your screenshots below this section. Replace the placeholder titles with actual descriptions.**

### Screenshot 1: Jenkins Dashboard

### Screenshot 2: Build Pipeline View

### Screenshot 3: Job Execution Logs

### Screenshot 4: Successful Deployment Confirmation

## Conclusion

This CI/CD setup ensures automated, repeatable, and reliable software delivery triggered directly from source code changes. It helps maintain consistency, reduces manual interventions, and increases deployment efficiency.

---

**Author:** *Your Name*
