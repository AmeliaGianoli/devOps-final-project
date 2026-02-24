# Containerization
## Docker
### Basics:
docker pull [download an image]  
docker run [run container from image]  
docker ps -a [shows running containers -including stopped]  
docker stop [stops running container]  
docker start [starts stopped container]  
docker rm [removes container]  
docker exec -it [executes a shell inside a running container]  

## Docker Compose
### Final project compose file 
Docker Compose Setup Documentation

This Docker Compose file runs three services: a documentation server, a MySQL database, and a Joomla CMS. All services are connected via a custom Docker network.

Services
1. Documentation Server

Service Name: documentation

Container Name: doc-final-project

Image: kobucom/pandoc:local1

Ports: 8081:80 (host → container)

Volumes: /home/ec2-user/devOps-final-project → /usr/local/apache2/htdocs

Network: final-network

Restart Policy: unless-stopped

Description:
Runs a Pandoc documentation server. Local project files are mounted so changes on the host are reflected in the server. Accessible at http://<host-ip>:8081.

2. MySQL Database

Service Name: database

Container Name: database-final-project

Image: mysql:8.0

Environment Variables:

MYSQL_ROOT_PASSWORD=Password99!

MYSQL_DATABASE=cms

Volumes: mysql-final-data:/var/lib/mysql

Network: final-network

Restart Policy: unless-stopped

Description:
Provides a MySQL database for Joomla CMS. Data is persisted using a named volume so it survives container restarts.

3. Joomla CMS

Service Name: cms

Container Name: joomla-final-project

Image: joomla:latest

Ports: 8090:80 (host → container)

Environment Variables:

JOOMLA_DB_HOST=database

JOOMLA_DB_USER=root

JOOMLA_DB_PASSWORD=Password99!

JOOMLA_DB_NAME=cms

Volumes: web-final-data:/var/www/html

Depends On: database

Network: final-network

Restart Policy: unless-stopped

Description:
Runs Joomla CMS connected to the MySQL database. Accessible at http://<host-ip>:8090. depends_on ensures Joomla starts after the database.

Networks

Network Name: final-network

Driver: bridge

Description:
Provides internal connectivity for all services.

Volumes
Volume Name	Container Path	Driver
mysql-final-data	/var/lib/mysql	local
web-final-data	/var/www/html	local

Description:
Persists MySQL database data and Joomla web files across container restarts.

Usage

Start all services:

docker-compose up -d

Check running containers:

docker-compose ps

Access services:

Documentation server → http://<host-ip>:8081

Joomla CMS → http://<host-ip>:8090

Stop all services:

docker-compose down