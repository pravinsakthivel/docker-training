## Dockerfile Demo
---

1. Create a directory "nginx-demo"
2. Open nginx-demo in CMD prompt
3. Open VS Code or ATOM or Notepad++ with folder nginx-demo
4. Create a new HTML file "index.html" inside "nginx-demo"

    ```
    <h1>Welcome to Containerized Application</h1>
    <p>The quick brown fox jumps over the lazy dog. </p>
    ```

5.  Create a new file "Dockerfile" (Case sensitive filename)

    ```
    FROM nginx:1.7.9
    COPY index.html /usr/share/nginx/html/
    ```

6.  Switch to CMD prompt (Refer #2)

    ```
    $ docker build -t {DOCKERUSERID}/mywebsite2:v1 .  
    ```

7.  Test the newly built image

    ```
    $ docker run --name web2  -d -p 8000:80 {DOCKERUSERID}/mywebsite2:v1
    ```

8.  Test URL in Browser

    http://localhost:8000

9.  Open "index.html" file and make some changes.
10. To Update the container image:

    ```
    $ docker stop web2
    $ docker rm web2
    $ docker build -t {DOCKERUSERID}/mywebsite2:v1 .  
    $ docker run --name web2  -d -p 8000:80 {DOCKERUSERID}/mywebsite2:v1   
    ```