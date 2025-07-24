# MYSQL and PHPMyAdmin docker-compose file

Dockerfile with MYSQL and PHPMyAdmin. The changes will be updated on the data subfolder of our project, to persist data between sessions.

## Requirements:
- Internet connection
- Docker
- Docker compose

## Instructions:
'sudo docker compose up' from the path where this repository was downloaded for creating (if required) and launching the dockers containers.

## Notes:
- The .env variables will have been defined before to launch for the first time.
- In case you change .env variables after the first start (a test start) you will need to delete 'data' folder with the new configuration. In that case, it will be recommended to prune all the related containers / networks / images.

## Scripts:
- This repository includes the starter script for the correct management of the database, with all the information to work with (the main tables from the database).
    

# Ubuntu / Linux service config to setup dockers on launch

## Setup:
- We will change the '${your_folder}' string on the 'start-mysql-pma-server.sh' for the absolute folder path where this repository was downloaded.
- We will copy the file 'service-config/start-mysql-pma-server.sh' with the script for launch the docker at startup in: 'usr/local/bin'.
- We will give execution permissions to the file with chmod x once it is copied to the path.
- We will copy the file 'service-config/mysql-pma-server-docker.service' to: '/etc/systemd/system/'.
- We will enable the service with 'sudo systemctl enable 'mysql-pma-server-docker.service'.
- We will start the service with 'sudo systemctl start 'mysql-pma-server-docker.service'.

From now on, those dockers will be launched on every machine reboot :)