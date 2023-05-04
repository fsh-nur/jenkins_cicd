## Launching a Jenkins server on an EC2 Instance

<details>
<summary>Prerequisites</summary>
<br>
- Have a .pem file available
</details>

1. Launch an EC2 instance with the following security groups and name it something like `fatima-tech221-master`:
2. Make sure to choose Ubuntu-Linux environment
3. Make sure to choose `t2.medium`
4. Choose `tech221` key pair 
5. `ssh` into instance 
6. Install Java:

```
 sudo apt install openjdk-11-jre

```
7. Install Jenkins into your instance according to your Ubuntu version. E.g for 20.04 follow these commands:

```
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update 
sudo apt install jenkins
sudo systemctl start jenkins 
sudo apt install jenkins 
sudo service jenkins start
systemctl status jenkins.service

```

8. Search the instance IP in your browser on the `:8080` port
9. This will open the Jenkins interface where it will ask you to imput your password located in this folder which you can navigate to using this command:

```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
10. Select `Install suggested plugins`
11. You may skip this and continue as administrator at this point, or create a user.
12. Click `Available plugins` and select the following extensions make sure you choose `Install without restart` each time =>


- Amazon EC2 Plugin
- NodeJS Plugin
- Office 365 Connector
- SSH Agent Plugin

13. In order to allow our tests to run in our instance make sure to configure to the NodeJS extension by navigating to the Global Configuration and amending it:


14. Once the extensions have been sorted out we can connect our EC2 Instance with our GitHub Key. Now we navigate to the `Dashboard`, select `Manage Jenkins` and select `Manage nodes and clouds` and click on `Configure Clouds`, add a new cloud and add `Amazon EC2`.


15. Click `add` under Amazon EC2 Credentials and Select `Jenkins`:
```
Jenkins Credentials Provider: Jenkins
Kind: AWS Credentials

```
16. Select your rehion as `eu-west-1`
17. under EC2 Pair's Pribvate Key select Jenkins, as well as `SSH username th private key` and name is under `tech221_pem`. This is where the pem file will end up going. Select `Enter Directly` under Private key then add your pem file. 
18. 18 Test the connection if successful then save.
19. Now we have the Jenkins dashboard and we have downloaded all extensions we may begin to create our Jobs such as starting our Sparta App, where we will create an instance similar to previous steps, however allow the jenkins server IP SSH into the Sparta App Instance to allow us to build a pipeline.



