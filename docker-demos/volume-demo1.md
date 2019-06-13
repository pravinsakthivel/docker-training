# Volume Demo

Volumes are assignable directories/folders to containers.

How to set volume?

$ docker run -d -p 8080:80 -v "D:\GitHub\docker-ofss-june-2019\docker-demos\nginx-demo2":"/usr/share/nginx/html" nginx:1.7.9

$ docker run -d -p 9000:80 -v "D:\GitHub\docker-ofss-june-2019\docker-demos\nginx-demo2":"/usr/share/nginx/html" nginx:1.7.9

Syntax:
    -v "Host Directory":"Guest Directory" 

Volumes can be assigned only from DOCKER RUN command.
Once created, container can not be linked with new volume. 