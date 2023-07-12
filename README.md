# CICD-Pipeline-using-AWS-services
![](https://github.com/SouravBose42/CICD-Pipeline-using-AWS-services/blob/main/CICD.gif)

```bash
#!/bin/bash 
# This installs the CodeDeploy agent and its prerequisites on Ubuntu 22.04.  
sudo apt-get update 
sudo apt-get install ruby-full ruby-webrick wget -y 
cd /tmp 
wget https://aws-codedeploy-us-east-1.s3.us-east-1.amazonaws.com/releases/codedeploy-agent_1.3.2-1902_all.deb 
mkdir codedeploy-agent_1.3.2-1902_ubuntu22 
dpkg-deb -R codedeploy-agent_1.3.2-1902_all.deb codedeploy-agent_1.3.2-1902_ubuntu22 
sed 's/Depends:.*/Depends:ruby3.0/' -i ./codedeploy-agent_1.3.2-1902_ubuntu22/DEBIAN/control 
dpkg-deb -b codedeploy-agent_1.3.2-1902_ubuntu22/ 
sudo dpkg -i codedeploy-agent_1.3.2-1902_ubuntu22.deb 
systemctl list-units --type=service | grep codedeploy 
sudo service codedeploy-agent status


 
<br>## Special Note:<br>
<br>Use Ubuntu while creating EC2 instance<br>
<br>Connect the instance and type vim install.sh(paste the above script,save and exit)<br>
## wget https://aws-codedeploy-us-east-1.s3.us-east-1.amazonaws.com/releases/codedeploy-agent_1.3.2-1902_all.deb
<br>Make sure to modify the Availablity zone according to your use like here it is (us-east-1) for North virginia<br>
<br>if you are using Mumbai then replace that place with (ap-south-1)<br>
<br>type- bash install.sh

<br>⭕Hope it you help you for your practice project.Thank you🤗.<br>
