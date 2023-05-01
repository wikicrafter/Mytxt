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

___

##### Linux 
<p>some popular Linux automation tools:</p>
<ol>
<li>
<p>Ansible - A configuration management tool that automates IT infrastructure provisioning, configuration management, and application deployment.</p>
</li>
<li>
<p>Puppet - A configuration management tool that automates IT infrastructure management and software deployment.</p>
</li>
<li>
<p>Chef - A configuration management tool that automates IT infrastructure provisioning, configuration management, and application deployment.</p>
</li>
<li>
<p>Jenkins - A popular open-source automation server that supports building, testing, and deploying software projects continuously.</p>
</li>
<li>
<p>SaltStack - A configuration management and remote execution tool that automates IT infrastructure provisioning, configuration management, and application deployment.</p>
</li>
<li>
<p>Terraform - An infrastructure-as-code tool that automates the provisioning and deployment of cloud resources across different cloud providers.</p>
</li>
<li>
<p>Docker - A containerization platform that enables developers to package applications and their dependencies into a single unit, making it easier to deploy and manage them.</p>
</li>
<li>
<p>Kubernetes - An open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications.</p>
</li>
<li>
<p>Nagios - A monitoring tool that automates the detection and resolution of network and server issues.</p>
</li>
<li>
<p>Zabbix - A monitoring tool that automates the detection and resolution of network and server issues.</p>
</li>
</ol>


###### Script based automation:
<p>here are some popular Linux scripting-based automation tools:</p>
<ol>
<li>
<p>Bash - A shell scripting language that is commonly used for automating tasks in Linux. It can be used to write scripts to automate tasks such as system administration, file management, and software deployment.</p>
</li>
<li>
<p>Python - A high-level programming language that is commonly used for automation tasks in Linux. It can be used to write scripts to automate tasks such as system administration, web scraping, and data analysis.</p>
</li>
<li>
<p>Perl - A scripting language that is commonly used for automation tasks in Linux. It can be used to write scripts to automate tasks such as system administration, text processing, and network programming.</p>
</li>
<li>
<p>AWK - A scripting language that is commonly used for automation tasks in Linux. It can be used to write scripts to automate tasks such as text processing and data analysis.</p>
</li>
<li>
<p>Sed - A stream editor that is commonly used for automation tasks in Linux. It can be used to write scripts to automate tasks such as text processing and data transformation.</p>
</li>
<li>
<p>Cron - A job scheduler that is commonly used for automation tasks in Linux. It can be used to schedule scripts and commands to run at specific times or intervals.</p>
</li>
<li>
<p>Expect - A scripting language that is commonly used for automation tasks in Linux. It can be used to write scripts to automate tasks such as interactive applications, network programming, and system administration.</p>
</li>
</ol>

###### Here is a simple script for linux bash shell:

```
#!/bin/bash

echo "System Information:"
echo "-------------------"

uname -a
lsb_release -a
free -h | grep "Mem"

echo ""
echo "CPU Information:"
echo "-----------------"

lscpu | grep "Model name"

echo ""
echo "Disk Information:"
echo "------------------"

lsblk

echo ""
echo "Network Information:"
echo "-------------------"

ip addr show | grep "inet "

echo ""
echo "Enabled Drivers:"
echo "-----------------"

systemctl list-unit-files | grep enabled

echo ""
echo "Disabled Drivers:"
echo "------------------"

systemctl list-unit-files | grep disabled

echo ""
echo "Enabled External Ports:"
echo "-----------------------"

netstat -tuln | grep "LISTEN" | awk '{print $4}' | cut -d':' -f2 | sort | uniq | xargs -I{} echo "Port {} is open"



```


___

##### Cloud Automation:

<p>cloud automation services:</p>
<ol>
<li>
<p>AWS CloudFormation: AWS CloudFormation is an infrastructure-as-code service that allows you to provision and manage AWS resources using templates. You can use CloudFormation to automate the deployment and management of your infrastructure on AWS.</p>
</li>
<li>
<p>Azure Automation: Azure Automation is a cloud-based automation service that allows you to automate the creation, deployment, and management of resources in Microsoft Azure. It provides a central location for managing automation assets such as runbooks, configurations, and modules.</p>
</li>
<li>
<p>Google Cloud Deployment Manager: Google Cloud Deployment Manager is a cloud-based automation service that allows you to define and deploy your Google Cloud Platform resources using configuration files. It provides a simple and repeatable way to create and manage your infrastructure on Google Cloud Platform.</p>
</li>
<li>
<p>Terraform: Terraform is an open-source infrastructure-as-code tool that allows you to define, provision, and manage infrastructure resources across multiple cloud platforms. It provides a simple and consistent way to manage your infrastructure as code.</p>
</li>
<li>
<p>Ansible: Ansible is an open-source automation tool that can be used to automate the creation and management of infrastructure resources across multiple cloud platforms. It provides a simple and efficient way to manage your infrastructure as code.</p>
</li>
<li>
<p>Chef: Chef is an open-source configuration management tool that can be used to automate the creation and management of infrastructure resources across multiple cloud platforms. It provides a simple and consistent way to manage your infrastructure as code.</p>
</li>
<li>
<p>Puppet: Puppet is an open-source configuration management tool that can be used to automate the creation and management of infrastructure resources across multiple cloud platforms. It provides a simple and consistent way to manage your infrastructure as code.</p>
</li>
<li>
<p>Kubernetes: Kubernetes is an open-source container orchestration tool that can be used to automate the deployment and management of containerized applications across multiple cloud platforms. It provides a simple and consistent way to manage your containerized applications as code.</p>
</li>
</ol>


___

Extra script for Windows, Here's an example script that will delete all files and subfolders in a specific folder permanently:

``` 
@echo off
set folder_path=C:\path\to\your\folder

echo Deleting all files and subfolders in %folder_path%...

REM Delete all files in the folder
del /f /q %folder_path%\*.*

REM Delete all subfolders in the folder
for /d %%i in (%folder_path%\*) do (
    rd /s /q "%%i"
)

echo Deletion complete.


```

