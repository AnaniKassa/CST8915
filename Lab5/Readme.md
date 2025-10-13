# About me 
### Full name: Anani Thierry Kassa
### Student ID: 041140713

## 1- Demo Video (Max 5 minutes)
https://youtu.be/UySffRnfe7Q

## 2- Final docker-compose.yaml file which uses the images from your docker hub.

     

## 3- Notes about setup challenges or lessons learned.
- Make sure every port is not used by other process while running the docker compose file 
- check with ```sudo lsof -i :<port number>```
- kill each process that show up: ```sudo kill -9 <process ID>```
- Stop and remove all Docker resources: ```docker compose down --remove-orphans```
```docker rm -f $(docker ps -aq) 2>/dev/null```
- verify: ```docker ps```
- rebuild the docker compose file: ```docker compose up --build```



