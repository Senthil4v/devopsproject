# DevopsGit
Final project submission for Edureka/DevOps

------------------------------------------------------------------------------------------------------
**
On Master Server:**
1) Run master_setup.sh on you master VM, this will install all necessary tools needed for starting with the project.
2) Manually setup Java and Maven Path in /etc/profile, this will be added to jenkins
3) Add sudo/root permission for Jenkins user based on your OS
4) Once setup is completed use web browser on host machine "**https://<master_server_ip>:8080**" to open jenkins
    a) In Jenkin URL install plugins for Ansible and other dependencies
    b) Under global configuration setup the path to JDK, Ansible and Git
    c) In global credential input credentials used for Server, Git etc if needed
5) Also to ensure ansible is able to connect to each host, for this we need to setup SSH key and copy the key to respective user folder on slave machine

------------------------------------------------------------------------------------------------------

**
On Slave Server:**
5) create path for Jenkins workspace in my case i used and created a node in Jenkins with below working directory
    #mkdir -p /devops/workspace/
7) make sure this path is changed in "**slave_web_build.yml**" for docker to build images.

------------------------------------------------------------------------------------------------------
**
On Master Server:**

8) Additionally to avoid IPs in inventory i added hosts name and respective ips in /etc/hosts. THis will help name resolution
9) Label Master server as **masterNode** and slave server as **slaveNode** to match the pipepline script
10) Create a jenkins pipline job and use contents of the Jekins_pipeline to create the job
11) Execute the piple line job
12) Once completed access the website using **http://<slave_node_ip>:7777**
------------------------------------------------------------------------------------------------------

#######################################################################################################

Screen shot # 1 Jenkins execution

<img width="1433" alt="Screenshot 2021-07-26 at 2 54 24 PM" src="https://user-images.githubusercontent.com/86504705/127000638-414faa81-b5cb-49e7-a013-08b39eacc29a.png">


Screen shot # 2 Docker images and container

<img width="1037" alt="Screenshot 2021-07-26 at 2 48 01 PM" src="https://user-images.githubusercontent.com/86504705/127000769-ebaff3f9-92fa-451d-9ade-11872cd9a93a.png">

Screen shot # 3 Output website

<img width="1033" alt="Screenshot 2021-07-26 at 2 48 16 PM" src="https://user-images.githubusercontent.com/86504705/127000903-fa96c9b5-a237-410e-ac8b-eba291920de2.png">







