# Traefik 2.0

***Step by step manual:***
    
1. create network traefik (external: true, network name: __web__)
    ```bash
    $ docker network create web
    ```

2. Run traefik 2.0
 
    ```bash
   $ pwd;
   /home/project/traefik.docker
    $ docker-compose up -d
   ```

3. Copy docker-compose.example.yml to new project rename it to docker-compose.yml (or merge if it already exist) and custom it for your project
4. Include every services which you want to host into __web__ network:
   ```docker-compose.yml
   services:
     service-name:
       networks:
           - web 
   ```
5. Run docker into your project:
   ```bash
   $ pwd;
   /home/project/example.com
   $ docker-compose up -d
   ```
6. Check into project docker-compose.yml no external:true network are declared, except __web__

    For example you can:
    
    ```docker-compose.yml
    api_net:
      external: false
    ``` 
   
   \* api_net - some existed network into project (before treafik was added)