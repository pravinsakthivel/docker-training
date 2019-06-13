## Managing Docker Images

1.  Signup on Dockerhub https://hub.docker.com
2.  Using Docker CLI, Login into your account

    $ docker login
    Username: ______
    Password: ------

3.  Stop & Remove existing container

    $ docker stop web1
    $ docker rm web1

4.  Lauch a new container

    ```
    $ docker run -d --name web1 -p 8000:80 nginx:1.7.9  
    ```

5.  Attach to running container using:

    ```
    $ docker exec -it web1 bash
    ```

    NOTE: -it   Interactive Terminal
          bash  Command to run on startup
            For windows, use "cmd" or "powershell"
            For Linux, use "sh" or "bash"

5.  Switch to directory which contains default html page.

    ```
    $ cd /usr/share/nginx/html
    ```

6.  Modify the existing index.html page

    ```
    $ echo "<h2>Hello from Mahendra</h2>" > index.html
    $ exit
    ```

7.  Capture the existing container and convert into IMAGE

    ```
    $ docker commit -a {YOURNAME} web1 {DOCKERUSERID}/mywebsite1:latest   
    ```

    example:
    ```
    $ docker commit -a "Mahendra Shinde" web1 mahendrshinde/mywebsite1:latest   
    ```

8.  Upload the image

    ```
    $ docker push {DOCKERUSERID}/mywebsite1:latest
    ```

    example:
    ```
    $ docker push mahendrshinde/mywebsite1:latest
    ```

9.  To create new container

    ```
    $ docker run -d -p 8000:80 --name web1 {DOCKERUSERID}/mywebsite1:latest
    ```
    
    Example:
    ```
    $ docker run -d -p 8000:80 --name web1 mahendrshinde/mywebsite1:latest
    ```
