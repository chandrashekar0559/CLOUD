# CLOUD
1) Create new repository in GITHUB by GITBASH 
let's assume we've GITBASH windows open follow below steps:

git config --global user.name "GITHUBNAME"

git config --global user.email WHICH YOU GAVE ON GITHUB

going to folder

git init 

git add .

git commit -m "node based cloud messanger app"

git remote add origin https://github.com/chandrashekar0559/CLOUD.git

git push -u  origin master 

Hope , your project was reposited in GITHUB.

then,

2) Now install Puttty and Putty SSH key generation s/w

3) Let us assume we've AWS account and i'm logged into AWS then  gothrough ES2 follow below steps:

click Lunch instance , then will go step 1
 choose an AMI  in ubuntu free trail version , then will go step 2 

then click next move 2 steps , now in step 5 we're create TAG   KEY is NAME & Value is Some name  

then move to step6 , here if you want change security grup name.
next add rules give http, https, custom TCP rule .

IN Custom TCP RULE on port value change into your port numm ex:- 3000

then , in step7 change dropdown value DOWNLOAD KEY PAIR , if downloded is complted click lunch instances

4) Next open putty ssh generation S/w click load
Browse before we downloded key pair file 
then give security file 

and now open Putty , and take the port and auto login name from AWS 

for this , gothrough Connect to you instances popup will open there in example we've 

ssh-i "yourproject.perm" ubuntu@ec2-se-some-value-here

Copy after @value and paste into Puttty host name ex: ec2-se-some-value-here
then connectin under data on putty window

give auto-login username before @ ex:ubuntu

now click open button.

putty will connect to your AWS URI 

then fallow this steps on putty promt:

sudo apt-get update

5). now install node js on AWS server by using putty ubuntu:
curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install -y nodejs

6). now install MONGO DB on AWS server by using putty ubuntu: 
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6
echo "deb [ arch=amd64 ] http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list
sudo apt-get update
sudo apt-get install -y mongodb-org

mondodb is installed then run mondodb sevices 

sudo service mongod start

7)now install NGINX on AWS server by using putty ubuntu: 

sudo apt-get install nginx

sudo /etc/init.d/nginx start

cat /etc/nginx/sites-available/default

Let’s first remove the default config from sites-enabled, we will leave it in sites-available for reference.
sudo rm /etc/nginx/sites-enabled/default

Create a config file in sites-available and name it whatever you like.
sudo nano /etc/nginx/sites-available/messanger

server {
  listen 80;
  server_name messanger;
  location / {
    proxy_set_header  X-Real-IP  $remote_addr;
    proxy_set_header  Host       $http_host;
    proxy_pass        http://127.0.0.1:3000;
  }
}

sudo ln -s /etc/nginx/sites-available/messanger /etc/nginx/sites-enabled/messanger



8). now clone the github project
 git clone yourproject.git  then click enter
 
9). now goto ur project directory 
CD yourproject/ then click enter

10). Now install 'forever' by using 
sudo npm forever -g install command // this forever script for if restart session or we're exit the session still run the forever project 

11). Now run the server by using
forever start server.js 
above command thenserver started.

your project will start like this 

http://ec2-52-14-61-54.us-east-2.compute.amazonaws.com/
 
 




 










 

 







