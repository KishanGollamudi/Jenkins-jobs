# CI/CD Pipeline Using Jenkins and GitHub Webhooks

## Overview

This project demonstrates a complete CI/CD pipeline built using Jenkins. The pipeline automates the process of cloning source code, testing it, building it into deployable artifacts, and finally deploying it to the target environment.

## Source Code Repository

This pipeline uses the following GitHub repository as the source:

**Repository:** [https://github.com/KishanGollamudi/Java-Web-Calculator-App.git](https://github.com/KishanGollamudi/Java-Web-Calculator-App.git)

## Pipeline Stages

1. **Cloning Job**

   * Fetches the latest code from GitHub.
<img width="1920" height="1080" alt="16" src="https://github.com/user-attachments/assets/6c2b42c9-aac1-456e-9f24-53ee714a0594" />
<img width="1920" height="1080" alt="17" src="https://github.com/user-attachments/assets/0a8a68d3-157b-4352-a620-c6097e37cb06" />
<img width="1920" height="1080" alt="18" src="https://github.com/user-attachments/assets/8afbcaae-dd67-484d-8a71-60842f611121" />
<img width="1920" height="1080" alt="22" src="https://github.com/user-attachments/assets/d971561b-9645-4af5-b70c-6bebfc4dc6cc" />

2. **Test Job**

   * Executes automated tests to verify the integrity and functionality of the code.
<img width="1920" height="1080" alt="23" src="https://github.com/user-attachments/assets/b0a20702-cab5-42e4-9038-84b960ff581b" />
<img width="1920" height="1080" alt="24" src="https://github.com/user-attachments/assets/5924dc5d-e461-40b5-b569-4422f2d12b0a" />
<img width="1920" height="1080" alt="25" src="https://github.com/user-attachments/assets/ea6af38d-ffdc-4318-84f7-e16c785f47e3" />
<img width="1920" height="1080" alt="26" src="https://github.com/user-attachments/assets/9694034f-8b22-4a6f-97d3-b68c3852ddc3" />

3. **Build Job**

   * Builds the project and creates the output artifacts.
<img width="1920" height="1080" alt="27" src="https://github.com/user-attachments/assets/10ff86c5-fa5c-45b9-b302-055f67ec283d" />
<img width="1920" height="1080" alt="28" src="https://github.com/user-attachments/assets/3cd93b3d-3d46-4304-add1-88788f493485" />

4. **Deploy Job**

   * Deploys the final build to the target server/environment.
<img width="1920" height="1080" alt="29" src="https://github.com/user-attachments/assets/3a29c155-9b57-4d1f-bb3f-9576172bbca4" />
<img width="1920" height="1080" alt="33" src="https://github.com/user-attachments/assets/153dc49b-8511-4055-aa6f-e3c69968a696" />

## Server Details

The Jenkins server was hosted on an **AWS EC2 instance (t2.micro)**.
<img width="1920" height="1080" alt="1" src="https://github.com/user-attachments/assets/c1ddb37e-73c3-425b-932a-dad91e906b18" />

## Jenkins Installation Script

The following script was used to install Jenkins on an Ubuntu server:
<img width="1920" height="1080" alt="3" src="https://github.com/user-attachments/assets/e8974a42-5b28-4447-aa27-b7f25fefe54d" />

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
<img width="1920" height="1080" alt="4" src="https://github.com/user-attachments/assets/92667d99-01b0-4fa3-8987-1819e2e0c6b7" />
<img width="1920" height="1080" alt="5" src="https://github.com/user-attachments/assets/5d425dc8-c262-453e-be71-e3bc1e67689d" />
<img width="1920" height="1080" alt="6" src="https://github.com/user-attachments/assets/f2953f84-de78-409e-9200-247903a0c254" />

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

<img width="1920" height="1080" alt="36" src="https://github.com/user-attachments/assets/ac8ec640-ef3e-43d3-ad86-2e706def0736" />

<img width="1920" height="1080" alt="39" src="https://github.com/user-attachments/assets/87f8bea8-a1bf-41f1-8978-e7992c585ad5" />

7. Configured pipeline view to visualize and trigger jobs sequentially.

## GitHub Webhook Integration

* Configured a webhook in GitHub to notify Jenkins upon every code push.
* Jenkins automatically triggered the pipeline when changes were pushed.

<img width="1920" height="1080" alt="43" src="https://github.com/user-attachments/assets/3e71cb86-7e21-47d7-aa71-53aa2cd55732" />
<img width="1920" height="1080" alt="44" src="https://github.com/user-attachments/assets/1ba4af7c-f3d3-4856-99eb-446c46a7a25c" />
<img width="1920" height="1080" alt="45" src="https://github.com/user-attachments/assets/5797ca84-f7ed-4dcc-94da-23369468c68d" />
<img width="1920" height="1080" alt="46" src="https://github.com/user-attachments/assets/13816acd-1cef-4225-8676-2c994ae97892" />

## Pipeline Flow

```
GitHub Commit → Clone Job → Test Job → Build Job → Deploy Job
```
<img width="1920" height="1080" alt="41" src="https://github.com/user-attachments/assets/6b5a77dd-b6f5-4b56-a1e1-83c9e24c6733" />
<img width="1920" height="1080" alt="42" src="https://github.com/user-attachments/assets/898355af-71d7-4931-ae98-6459735778d2" />
<img width="1920" height="1080" alt="47" src="https://github.com/user-attachments/assets/62bd03d2-be70-4058-a084-91146d20574c" />
<img width="1920" height="1080" alt="48" src="https://github.com/user-attachments/assets/caac05f2-e727-4850-8b59-fd8e118e4b49" />
<img width="1920" height="1080" alt="49" src="https://github.com/user-attachments/assets/23a24d5f-953a-4bfb-903a-7c780c62f3d3" />

## Conclusion

This CI/CD setup ensures automated, repeatable, and reliable software delivery triggered directly from source code changes. It helps maintain consistency, reduces manual interventions, and increases deployment efficiency.

---

**Author:** *Kishan Gollamudi*
