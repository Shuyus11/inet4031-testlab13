# Docker Lab: Containerizing a Three-Tier Application  
**INET 4031 - Introductions to Systems**

## Overview
This project runs a three-tier application using Docker Compose. It includes:

- Apache (web) – handles incoming requests  
- Flask (app) – backend API  
- MariaDB (db) – database  

The application allows users to view and submit tickets through a web interface. Each service runs in its own container and communicates through Docker networking.



## Setup
- git clone https://github.com/Shuyus11/inet4031-lab12-docker.git
- cd inet4031-testlab12
- cp .env.example .env
- docker compose up --build




## Access
Open your browser and go to:

http://192.168.56.2/ 



## Features
- REST API (/api/tickets)  
- Persistent data using Docker volumes  
- Internal communication using service names  
- Health checks to ensure services are running properly  



## Useful Commands
- docker compose ps
- docker compose logs
- docker compose down
- docker compose down -v




## Author
Shu’ayb Yusuf  
INET 4031



