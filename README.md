# ansible_terra_ngx_destiny

ansible based terraform IAAS automated repo to easily run on any environment

ansible-nginx
Motive
ansible based ubuntu 20.04 LTS AMI for launch Nginx Server

Purpose
Exetel practice module

Problem
Reduce the burden of setting up the IAAS modules faster, accurate using a cook book

Learn
Ansible, terraform basics and improve AWS managed services knowledge

How to Use
1. git clone https://github.com/ruwendraben/ansible_terra_ngx_destiny.git

2. cd ansible_terra_ngx_destiny

3. Run Deployment script: ./deploy.sh

Note:- Ansible steps are contained under roles/web/nginx/tasks/main.yaml (Change as you wish) (Update and upgrade apt packages -> Install the nginx package -> Copy custom index.html file -> Edit Configuration in Nginx -> start the nginx service)

Note:- Nginx webcontent are located in roles/web/nginx/files/index.html (Paint as you wish)

Note:- configure proxy_pass inside roles/web/nginx/files/index.html Listener port (Config in webappserver): edit file /etc/nginx/sites-available/default {Listen port 9001} Proxy pass (Config in proxy server): edit file /etc/nginx/sites-available/default where location / { proxy_pass http://172.31.30.62:9001;} proxy_pass Server IP should be added to env/hosts file

Note:- configure host ip file: env/hosts ( example: [webservers] )

Note:- Install Ansible and add relevant keys to access AWS account

Note:- Deployment server you are running should be under the same region (ap-southeast-2), can change from main.tf file.
