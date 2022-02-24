# docker installation
|Sno.| reason|commands |
|--|--|--|
|1| update apt|sudo apt-get update|
|2|install packages|sudo apt-get install \ca-certificates \curl \gnupg \lsb-release|
|3|add docker key|curl -fsSL https://download.docker.com/linux/ubuntu/gpg | 
|4||sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg|
|5|set stable repository| echo \"deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \$(lsb_release -cs) stable" |
|6||sudo tee /etc/apt/sources.list.d/docker.list > /dev/null|
|7| update apt|sudo apt-get update|
|8|install docker engine|sudo apt-get install docker-ce docker-ce-cli containerd.io|
|9|check status if active then docker is running|sudo systemctl status docker|
# install mariadb and creating container
|Sno.| reason|commands |
|--|-|-|
|1| start dockerd dom. |sudo systemctl start docker|
|2|| sudo gpasswd -a "${USER}" docker|
|3|image download| docker search mariadb|
|4|create container name & mysql_root_pass can be change|docker run --name mariadbtest -e MYSQL_ROOT_PASSWORD=mypass -p 3306:3306 -d docker.io/library/mariadb:10.3|
|5|check container ur container name & id will be there |docker ps|
|6|to restart a container|docker restart your container name|
# entering container and creating database and table with  commands
|Sno.| reason|commands |
|--|-|-|
|1|to enter container mariadbtest container name can be changed|Docker exec -it mariadbtest bash|
|2|after running 1 command after # then enter password|mysql -u root -p|
|3|to create database|create database database name;|
|4|to enter database|use database name|
|5|create  table|create table table_name(att,subatt,testcase etc);
|6|to enter data in table|insert into table_name values( row wise values);
|7|to view table|select * from table_name;|


