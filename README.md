# CICD-Pipeline-using-AWS-services
![](https://github.com/SouravBose42/CICD-Pipeline-using-AWS-services/blob/main/CICD.gif)

✳#!/bin/bash 
✳✳# This installs the CodeDeploy agent and its prerequisites on Ubuntu 22.04.  
<code>sudo apt-get update<code> 
<code>sudo apt-get install ruby-full ruby-webrick wget -y <code>
<code>cd /tmp <code>
<code>wget https://aws-codedeploy-us-east-1.s3.us-east-1.amazonaws.com/releases/codedeploy-agent_1.3.2-1902_all.deb <code>
<code>mkdir codedeploy-agent_1.3.2-1902_ubuntu22<code> 
<code>dpkg-deb -R codedeploy-agent_1.3.2-1902_all.deb codedeploy-agent_1.3.2-1902_ubuntu22<code>
<code>sed 's/Depends:.*/Depends:ruby3.0/' -i ./codedeploy-agent_1.3.2-1902_ubuntu22/DEBIAN/control<code>
<code>dpkg-deb -b codedeploy-agent_1.3.2-1902_ubuntu22/ <code>
<code>sudo dpkg -i codedeploy-agent_1.3.2-1902_ubuntu22.deb<code> 
<code>systemctl list-units --type=service | grep codedeploy<code> 
<code>sudo service codedeploy-agent status<code>

✳✳✳#Special Note:
#wget https://aws-codedeploy-us-east-1.s3.us-east-1.amazonaws.com/releases/codedeploy-agent_1.3.2-1902_all.deb
<br>⭕Make sure to modify the Availablity zone according to your use like here it is (us-east-1) for North virginia<br>
<br> if you are using Mumbai then replace that place with (ap-south-1)<br>

⭕Hope it you help you for your practice project.Thank you🤗. 

