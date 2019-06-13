## ENV Variables to Run Postgres DB

1.  Pull postgres SQL image

    $ docker pull postgres

2.  Launch a new postgres database

    $ docker run --name postgresdb -e POSTGRES_PASSWORD=pass1234 -d postgres   

    -e POSTRGRE_PASSWORD    Password for the default user 'postgres'
    NOTE, No PORT mapping done here!

3.  Get IP address for postgres container

    $ docker inspect postgresdb

4.  From the output of last command, locate IPAdress and note it down.
    example : My Container had IP : 172.17.0.4

5.  Launch Adminer container (Only if not already running!)

    $ docker run -p 8080:8080 adminer

6.  Open Web browser and visit this URL:
    
    http://localhost:8080

    Provide following details:
        Server:     172.17.0.4      # IP Address of postgres container
        Username:   postgres        # Default postgres username
        Password:   pass1234        # Password assigned to container through ENV
        Database:   <EMPTY>         # DONT WRITE ANYTHING!
        