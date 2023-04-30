### Here we Go:

##### Automation tools Categories:
* Configuration management 
* Continuous Delivery 
* Monitoring 
* Version Control
* Code Test and Build
* Orchestration 

##### All tool categories fit into four generic categories:
* Infrastructure as a code 
* Continuous integraton/Deployment 
* Configuration/Secret Management 

___
<ol>
<li>
<p>Configuration Management Tools: These tools help automate the process of configuring, managing, and deploying software applications and infrastructure. Examples include Ansible, Chef, Puppet, and SaltStack.</p>
</li>
<li>
<p>Continuous Integration and Continuous Delivery (CI/CD) Tools: These tools automate the process of building, testing, and deploying software applications. Examples include Jenkins, CircleCI, Travis CI, and GitLab CI/CD.</p>
</li>
<li>
<p>Infrastructure as Code (IaC) Tools: These tools automate the process of provisioning and managing infrastructure resources using code. Examples include Terraform, CloudFormation, and Azure Resource Manager.</p>
</li>
<li>
<p>Monitoring and Alerting Tools: These tools automate the process of monitoring and alerting on system performance and availability. Examples include Nagios, Zabbix, Prometheus, and Grafana.</p>
</li>
<li>
<p>Security and Compliance Tools: These tools automate the process of ensuring compliance with security and regulatory requirements. Examples include Qualys, Nessus, and OpenSCAP.</p>
</li>
<li>
<p>ChatOps Tools: These tools automate the process of collaboration and communication between development and operations teams. Examples include Slack, Microsoft Teams, and Mattermost.</p>
</li>
<li>
<p>Robotic Process Automation (RPA) Tools: These tools automate repetitive and manual tasks using software robots. Examples include UiPath, Automation Anywhere, and Blue Prism.</p>
</li>
<li>
<p>Artificial Intelligence (AI) and Machine Learning (ML) Tools: These tools automate the process of analyzing and processing data using AI and ML algorithms. Examples include TensorFlow, PyTorch, and Scikit-learn.</p>
</li>
</ol>

___

<p>here are some commonly used DevOps automation tools:</p>
<ol>
<li>Configuration Management Tools:</li>
</ol>
<ul>
<li>Ansible</li>
<li>Chef</li>
<li>Puppet</li>
<li>SaltStack</li>
</ul>
<ol>
<li>Continuous Integration and Continuous Delivery (CI/CD) Tools:</li>
</ol>
<ul>
<li>Jenkins</li>
<li>CircleCI</li>
<li>Travis CI</li>
<li>GitLab CI/CD</li>
</ul>
<ol>
<li>Infrastructure as Code (IaC) Tools:</li>
</ol>
<ul>
<li>Terraform</li>
<li>CloudFormation</li>
<li>Azure Resource Manager</li>
<li>Pulumi</li>
</ul>
<ol>
<li>Containerization Tools:</li>
</ol>
<ul>
<li>Docker</li>
<li>Kubernetes</li>
<li>Helm</li>
<li>Nomad</li>
</ul>
<ol>
<li>Monitoring and Logging Tools:</li>
</ol>
<ul>
<li>Prometheus</li>
<li>Grafana</li>
<li>ELK Stack (Elasticsearch, Logstash, Kibana)</li>
<li>Datadog</li>
</ul>
<ol>
<li>Collaboration and Communication Tools:</li>
</ol>
<ul>
<li>Slack</li>
<li>Microsoft Teams</li>
<li>Mattermost</li>
<li>HipChat</li>
</ul>
<ol>
<li>Version Control Tools:</li>
</ol>
<ul>
<li>Git</li>
<li>GitHub</li>
<li>Bitbucket</li>
<li>GitLab</li>
</ul>
<ol>
<li>Code Quality and Security Tools:</li>
</ol>
<ul>
<li>SonarQube</li>
<li>Checkmarx</li>
<li>Veracode</li>
<li>Fortify</li>
</ul>
<ol>
<li>Cloud Platforms and Services:</li>
</ol>
<ul>
<li>Amazon Web Services (AWS)</li>
<li>Microsoft Azure</li>
<li>Google Cloud Platform (GCP)</li>
<li>DigitalOcean</li>
</ul>

___

<p>some commonly used automation tools for Windows operating system:</p>
<ol>
<li>
<p>PowerShell: This is a powerful command-line tool and scripting language designed for Windows automation. It allows you to automate a wide range of administrative tasks using scripts and cmdlets.</p>
</li>
<li>
<p>Task Scheduler: This built-in Windows tool allows you to schedule tasks to run automatically at specified times or events. You can use it to automate repetitive tasks like backups, system maintenance, and software updates.</p>
</li>
<li>
<p>Windows PowerShell Desired State Configuration (DSC): This is an extension to PowerShell that enables you to define the desired state of a Windows system using configuration files. It allows you to automate the deployment and configuration of software and infrastructure resources.</p>
</li>
<li>
<p>Microsoft System Center Configuration Manager (SCCM): This is a comprehensive tool for managing and deploying Windows systems, applications, and updates. It allows you to automate the deployment of software, patches, and updates to multiple systems.</p>
</li>
<li>
<p>Microsoft Deployment Toolkit (MDT): This is a free tool for automating the deployment of Windows operating system images. It allows you to create and customize Windows images for deployment across multiple systems.</p>
</li>
<li>
<p>AutoHotkey: This is a free, open-source tool for automating repetitive tasks on Windows. It allows you to create macros and scripts to automate keystrokes, mouse clicks, and other actions.</p>
</li>
<li>
<p>Macro Recorder: This is a tool that allows you to record and playback mouse and keyboard actions. It can be useful for automating repetitive tasks like data entry, form filling, and testing.</p>
</li>
<li>
<p>WinAutomation: This is a commercial tool for automating Windows applications and tasks. It allows you to create macros and scripts to automate tasks like data entry, web scraping, and file management.</p>
</li>
</ol>

___

#### Here I'm gonna show basic example of CMD script which show all info about system:
```
@echo off

echo System Information:
echo -------------------

systeminfo | findstr /C:"Host Name" /C:"OS Name" /C:"OS Version" /C:"System Manufacturer" /C:"System Model" /C:"Total Physical Memory"

echo.
echo CPU Information:
echo -----------------

wmic cpu get name

echo.
echo Disk Information:
echo ------------------

wmic diskdrive get name,model,size

echo.
echo Network Information:
echo --------------------

ipconfig | findstr IPv4

pause


```

<p>Explanation:</p>
<ul>
<li>The first part of the script is the same as before, displaying the system information and adding the Total Physical Memory.</li>
<li><code>echo.</code> - This command displays a blank line.</li>
<li><code>echo CPU Information:</code> - This command displays a header for the CPU information section.</li>
<li><code>echo -----------------</code> - This command displays a separator line.</li>
<li><code>wmic cpu get name</code> - This command retrieves the name of the CPU on the system using Windows Management Instrumentation (WMI).</li>
<li><code>echo.</code> - This command displays a blank line.</li>
<li><code>echo Disk Information:</code> - This command displays a header for the disk information section.</li>
<li><code>echo ------------------</code> - This command displays a separator line.</li>
<li><code>wmic diskdrive get name,model,size</code> - This command retrieves the name, model, and size of all disk drives on the system using WMI.</li>
</ul>




