## Using volumes with MySQL Database

### Given MySQL Database container :

```
$ docker run -d --name mysqldb -v "D:\mydata":"/var/lib/mysql"
        -e MYSQL_USER=mahendra -e MYSQL_PASSWORD=pass1234 
        -e MYSQL_ROOT_PASSWORD=pass12345
        -e MYSQL_DATABASE=mydata
        mysql:5.7

```

$ docker run -d --name my1 -v "D:\mydata":"/var/lib/mysql"
        -e MYSQL_USER=mahendr -e MYSQL_PASSWORD=pass1234 
        -e MYSQL_ROOT_PASSWORD=pass1244645
        -e MYSQL_DATABASE=mydata
        mysql:5.7


- Launch adminer, and connect to this MYSQL Database
- Create a sample table, add few records

- Next, delete the mysql container

- Create the new MYSQL database using the same command

- Connect using adminer 
        Database:   db          # or else use IP from mysqldb container
        Username:   mahendra
        Password:   pass1234
        Database:   mydata

- Just run SQL SELECT command to get records

