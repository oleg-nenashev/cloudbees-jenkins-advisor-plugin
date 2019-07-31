# CloudBees Jenkins Advisor Plugin

[![CloudBees Jenkins Support](https://img.shields.io/badge/Supported%20by-CloudBees-blue.svg?logo=cloudbees)](https://www.cloudbees.com/products/cloudbees-jenkins-support)

Periodically uploads [support bundles](https://wiki.jenkins.io/display/JENKINS/Support+Core+Plugin) for processing by CloudBees Jenkins Advisor.

To configure your Advisor uploads - *Manage Jenkins > CloudBees Jenkins Advisor*.

## Project Tracking

* Jenkins JIRA

## Build Job

* You can see the plugin's build status [here](https://ci.jenkins.io/job/Plugins/job/cloudbees-advisor-plugin/).

## Configuration

### System Properties

#### CloudBees Jenkins Advisor Upload Recurrence Period

Cannot be overridden at runtime. Requires restart to take effect. Defaults to 24hrs.

Overriding with Java System Property:

```bash
-Dcom.cloudbees.jenkins.plugins.advisor.BundleUpload.recurrencePeriodHours=1
```

#### CloudBees Jenkins Advisor Upload Timeout

Can be overridden dynamically at runtime, via Script Console:

```java
System.setProperty("com.cloudbees.jenkins.plugins.advisor.client.AdvisorClientConfig.advisorUploadTimeoutMinutes", "120");
```

Settings are lost after restart.

Can be permanently added by amending Jenkins Java System Properties:

```bash
-Dcom.cloudbees.jenkins.plugins.advisor.client.AdvisorClientConfig.advisorUploadTimeoutMinutes=120
```

Defaults to 60 (minutes)
