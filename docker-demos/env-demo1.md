## ENVIRONMENT VARIABLES
A Host can pass information to containers using ENVIORNMNET VARIABLES.
ENV can be passed only at the time of creation. Once container is launched, No NEW ENV can be passed from host to container.


1. Create a simple container with few ENV variables

    $ docker run -it -e "OWNER=Mahendra"
            -e "ADDRESS=Mumbai"
            --name test1 
            alpine
            sh

2.  Once inside the container, try following commands

    $ echo $OWNER
    $ echo $ADDRESS
    $ exit

    NOTE: On Windows containers, ENV variables are enclosed in % and %
    Example:
        echo %OWNER%
        echo %ADDRESS%
        exit

3.  Lets try with MYSQL Database

    $ docker pull mysql:5.7

4.  Create a new MySQL database with Username: mahendra password: pass1234 and DB mydata

    $ docker run --name mydb -e MYSQL_USER=mahendra             # custom user name
                            -e MYSQL_ROOT_PASSWORD=rootpass1234 # ROOT user password
                            -e MYSQL_PASSWORD=pass1234  # User 'mahendra' password
                            -e MYSQL_DATABASE=mydata    # name of database
                            -p 3306:3306        # port forwarding 
                            -d                  # run in background
                            mysql:5.7           # IMAGE used for provisioning container
    
    NOTE: Please remove all comments and line breaks from above command before 
            you try to execute it.

5.  TRY IT YOURSELF

    Try creating container instance for either postgreSQL or MS-SQL.
    HINT: Read documentation on hub.docker.com
