# LinuxServerConfiguration
The Last Project on my Nanodegree Program at Udacity 

- Linux server configuration and deploying project is the last project of nanodegree . I made this readme for 
  describing the steps to make this project with all configuration required 
# The ssh port for this project 
- 2200

# URL and IP
        
- URL -> http://ec2-13-59-1-189.us-east-2.compute.amazonaws.com/
- IP  -> http://35.158.93.110/ 


# user grader that I have made as the following 
- add grader ->  sudo adduser grader  
- make it sudoers - > sudo nano /etc/sudoers.d/grader
- serach for grader All=(ALL:ALL) ALL

# change my port 
- go -> sudo nano /etc/ssh/sshd_config
- search for port  (Port 22) to (Port 2200)
- login with the new port   -> ssh grader@35.158.93.110 -p 2200

# update packages
- update ->  sudo apt-get update
- upgrade ->  sudo apt-get upgrade

# configure my firwall 
-  ssh sudo ufw allow ssh
-  ssh port 2200  -> sudo ufw allow 2200/tcp 
-  port 80 -> sudo ufw allow www
-  port 123 -> sudo ufw allow ntp 
-  ufw  ->sudo ufw enable

# block remote login 
- go to config  -> sudo nano /etc/ssh/sshd_config
- search for    -> PermitRootLogin  yes and 
- change             to PermitRootLogin  no 
- save changes  -> service ssh restart

# login by key for security (key based)
- with file i will put it in the repository  called tes.pem
- and you can login with ssh -i tes.pem  grader@35.158.93.110 -p 2200
- where tes.pem is my file in this project 

# only key login 
- run that -> sudo nano /etc/ssh/sshd_config
- search for  that ->  (PasswordAuthentication yes)  to (PasswordAuthentication no)
- restart  -> sudo service ssh restart

# I installed some applications 

- Flask 
- postgresql
- Apache 
- mod_wsgi
- Git
- pip 
- virtual environment

# git project from github  
- go to -> cd /var/www
- make directory - > sudo mkdir catalog
- clone my project from github 
- doing some configuration 
- after restarting `apache` and checK IP it works 
