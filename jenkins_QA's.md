
# Jenkins Interview Questions and Answers

This document contains commonly asked Jenkins interview questions with detailed answers.

---

## 💡 What do you mean by Build?
A **Build** is the process of converting source code into executable software. It includes steps like compilation, testing, packaging, and deployment.

---

## 🔄 What is CI?
**CI (Continuous Integration)** is a development practice where developers integrate code into a shared repository frequently, ideally several times a day. Each integration is verified by automated builds and tests.

---

## ⚙️ How CI works? How do people work day to day?
CI involves:
- Developers push code to a shared repo (e.g., Git).
- Jenkins detects changes via webhooks or polling.
- Jenkins builds the code, runs tests, and deploys.
- Teams get immediate feedback and fix issues early.

---

## 📋 Prerequisites for CI
- Source Code Management (SCM) system like Git.
- Build tools (Maven, Gradle, etc.).
- CI server (e.g., Jenkins).
- Automated test framework.
- Sufficient hardware/resources.

---

## 🔧 Which tool do you use for CI? And how it works?
**Jenkins** is commonly used. It:
- Monitors version control systems.
- Triggers builds on changes.
- Integrates with build tools and test suites.
- Can deploy code using plugins or scripts.

---

## 🔁 Difference between SVN and Jenkins
| Feature      | SVN                      | Jenkins                  |
|--------------|---------------------------|---------------------------|
| Type         | Version Control System     | CI/CD Tool               |
| Function     | Stores source code         | Automates builds, tests, deployments |
| Role         | Manages code history       | Executes pipelines/jobs  |

---

## ▶️ What do you mean by running builds?
Running a build means executing a predefined sequence (job) in Jenkins like compile, test, and package the application.

---

## 🔌 Plugins used in Jenkins
- Git plugin
- Maven integration plugin
- Pipeline
- Docker
- Email extension
- Slack notifications

---

## 🛠️ Have you created Jenkins job from scratch?
Yes. Go to:
- Jenkins Dashboard → New Item → Freestyle or Pipeline → Configure build steps, SCM, triggers, etc.

---

## 🧰 Have you setup Jenkins? How did you install it?
Yes. Installation on Linux (CentOS/Ubuntu):
```bash
wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
yum install jenkins java-11-openjdk -y
systemctl enable jenkins
systemctl start jenkins
```

---

## 🕹️ How do you start Jenkins as a service?
```bash
systemctl start jenkins
```

---

## 🌐 How do you change Jenkins port? What is the default?
- Default port: **8080**
- To change: Edit `/etc/sysconfig/jenkins` or `/etc/default/jenkins`:
```bash
JENKINS_PORT=1234
```
Then restart Jenkins.

---

## 🔄 How to Start/Stop/Restart Jenkins?
```bash
systemctl start jenkins
systemctl stop jenkins
systemctl restart jenkins
```

---

## 📄 Where to find Jenkins logs?
Default location:
```bash
/var/log/jenkins/jenkins.log
```

---

## 🛠️ Challenges faced while setting up Jenkins
- Plugin compatibility
- Java version issues
- Port conflicts
- Memory allocation
- Permission issues

---

## 🔍 How to verify if Jenkins is running?
```bash
systemctl status jenkins
netstat -tulnp | grep 8080
```

---

## 🚫 How to stop Jenkins during builds?
Jenkins does not recommend stopping during active builds. You can:
```bash
systemctl stop jenkins
```
Or manually abort builds from Jenkins UI.

---

## 🔄 How to migrate Jenkins to another machine?
1. Copy JENKINS_HOME from old server
2. Install Jenkins on new server
3. Replace the new `JENKINS_HOME` with backup
4. Restart Jenkins

---

## 🗂️ Jenkins stores config at:
- Global: `$JENKINS_HOME/config.xml`
- Jobs: `$JENKINS_HOME/jobs/<job_name>/config.xml`

---

## 📁 Default Jenkins Home Directory
- Usually: `/var/lib/jenkins`
- To change:
```bash
export JENKINS_HOME=/new/path
```

---

## 🔙 How to restore Jenkins configuration?
Restore `JENKINS_HOME` backup including `jobs`, `plugins`, and `config.xml`

---

## 🧪 Changing JDK for all Jenkins jobs
Use Global Tool Configuration:
- Add new JDK under Jenkins → Manage Jenkins → Global Tool Configuration
- Use Job DSL or shared libraries to update all jobs programmatically.

---

## 📂 Number of job files in Jenkins
Each job has its own folder under `$JENKINS_HOME/jobs/`. Depends on number of jobs created.

---

## 🛠️ How to create Jenkins job and setup CI/CD?
- Create new job (Freestyle or Pipeline)
- Connect to Git
- Add build steps (Maven/Gradle)
- Post build (deploy with SCP, Docker, etc.)

---

## 📦 How many builds do you store?
- Controlled by "Discard Old Builds" setting in job configuration.

---

## ⚙️ What is Parameterized Build?
Allows passing parameters (e.g., environment, version) at build time.

---

## ☕ Running jobs with different JDKs?
Define multiple JDKs in Global Tool Configuration and select per job.

---

## ❌ Can Jenkins be used for non-Java apps?
Yes. Jenkins supports Python, Node.js, .NET, etc. using plugins and scripts.

---

## 🕰️ What is `cron` and `cron scm`?
- `cron`: Schedule job with a fixed time pattern.
- `cron scm`: Poll SCM periodically to check for changes.

---

## 🔐 Configuring Jenkins Security
- Go to Manage Jenkins → Configure Global Security
- Use Jenkins' own user database or external like LDAP.

---

## 🧾 What is Matrix-based Security?
Permission model where access is granted per user/role per function (job, node, etc.).

---

## 🔄 Trigger Jenkins build on VCS change
- Use **webhooks** (recommended)
- Use **Poll SCM** with schedule

---

## 📥 Plugin Installation
- Manage Jenkins → Plugins → Available → Select & Install
- Manual: Download `.hpi` file and place in `$JENKINS_HOME/plugins/`

---

## 💾 Do you backup Jenkins?
Yes. Backup:
- `$JENKINS_HOME`
- Jobs
- Config files
- Plugins

---

## ▶️ Manually start or trigger a build
- From Jenkins Dashboard → Job → Build Now
- Or using REST API / CLI

---

## 🔃 What is Reload Configuration from Disk?
Reloads all configurations without restarting Jenkins from files on disk.

---

## 💻 Start Jenkins from CLI
```bash
java -jar jenkins.war
```

---

## 📂 Backup only job configs (not workspace)?
Yes. Copy:
```bash
$JENKINS_HOME/jobs/<job_name>/config.xml
```

---

## 🔌 Install Jenkins Plugin Manually?
1. Download `.hpi` from Jenkins plugin site.
2. Place in `$JENKINS_HOME/plugins/`
3. Restart Jenkins.

---

**Prepared for Jenkins DevOps Interview.**
