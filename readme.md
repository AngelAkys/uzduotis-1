# nginx # php 7.0 # mysql 5.6.39 # Ubuntu 16.04.6

#tip work as root type# " sudo - " #

# install docker-compose # " sudo curl -L https://github.com/docker/compose/releases/download/1.18.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose " #
# " sudo chmod +x /usr/local/bin/docker-compose " # and restart pc or virtual machine# type " docker-compose --version " to make sure it's instaled #

# pull website files from github and put then into "src" folder# 
# " git clone https://github.com/adeoweb/devops-workshop /src " #  
# if you already have them just put into "src" folder # 
# mv %website files% /src #

# put "docker-compose.yml" and "site.conf" into / directory # mv docker-compose.yml / #  mv site.conf / #

# go to / and run command "sudo docker-compose up -d" # 

# run this commands:

 " docker exec -i default_php_1 bash -c "cd /src && composer install " # installS necesary libraries#

 then 

# edit .env file it's in src file change URL with " DATABASE_URL=mysql://mysql:mysql@db:3306/baze "
# " cd /src " # " nano .env " #

# edit doctrine.yaml it's in src/config/packages and change lines pdo_sqlite with pdo_mysql and version to 5.6.39
# " cd /src/config/packages " # " nano doctrine.yaml " #

and run these commands

# " docker exec -i default_php_1 bash -c "cd /src && bin/console doctrine:schema:update --force " #

# " docker exec -i default_php_1 bash -c "cd /src && bin/console doctrine:fixtures:load " #

# go to browser type localhost:1997 to enter website #

# to shutdown site type " sudo docker-compose down " #

# if you have any issuses or notices please contact DevOps we will kindly help you #

