Install Ubuntu Server 16.04 on online.net

Local machine generate ssh-keygen into ~/.ssh/id_rsa_domain

make file ~/.ssh/config with lines:
Host domain
	HostName	domain
	Port	 	22
	User		mishi
	IdentityFile	~/.ssh/id_rsa_domain


connect ssh-copy-id
ssh domain

change passwd: passwd

sudo apt-get update
sudo apt-get upgrade


#add docker repository
sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
sudo apt-get install software-properties-common
sudo apt-add-repository 'deb https://apt.dockerproject.org/repo ubuntu-xenial main'
sudo apt-get update

#verify its from docker repo, look apt.dockerproject

sudo apt-get install -y docker-engine
sudo systemctl status docker
#add user to docker group
sudo usermod -aG `whoami`

#logout and in again
exit
ssh triac
#verify
sudo docker run hello-world


#run docker interactive tty
docker run -it ubuntu


#list docker container
docker ps

#list active inactive
docker ps -a

#list most recent created
docker ps -l

#stop docker container
docker stop $id


sudo apt-get install python-pip
sudo pip install --upgrade pip
sudo pip install setuptools
sudo pip install docker-compose




#goto bitbucket and set deploymentkey
ssh-keygen
cd ~


git clone git@github.com:microuser/regexpatterns




cd ~/regexpatterns
sudo docker-compose up


lets make a systemd
sudo nano /etc/systemd/system/docker-compose.service


[Unit]
Description=DockerCompose
Requires=docker.service
After=docker.service

[Service]
Restart=always
ExecStart=/usr/local/bin/docker-compose -f /home/$USER/regexpattens/docker-compose.yml up 
ExecStop=/usr/local/bin/docker-compose -f /home/$USER/regexpatterns/docker-compose.yml stop

[Install]
WantedBy=default.target





sudo systemctl start docker-compose.service 
sudo systemctl status docker-compose.service 

sudo systemctl stop docker-compose.service 
sudo systemctl status docker-compose.service 

sudo systemctl enable docker-compose.service 





#----------------------------------------
Downlaod Sublime Text

Download the JDK with netbeans (not just netbeans), see text at bottom of downlaod page
open netbeans
Menu -> Tools -> plugins -> update
add plugins:
Editor Zoom
JSON Navigator
PHP Enhancements
Composer
PhpDocumentor 2
ApiGen
PHPUnit
PHP
NetbeansRegexPlugin
Git toolbar








