### How to prepeare your local database

1. Download and install [PostgreSQL](https://www.postgresql.org/download/). Optionally, you can download and install [pgAdmin 4](https://www.pgadmin.org/download/) which is an administration and development platform for PostgreSQL.
2. Clone or download application database backup file form here https://github.com/kverchi/diary-db-backup.git
3. Create the database with name *diary*
4. Restore postgresql backup file *diary-v2.0.tar* on your local Postgresql server for newly created database *diary*. [How to restore backup](https://www.postgresql.org/docs/9.6/backup-dump.html#BACKUP-DUMP-RESTORE) 
    
### How to deploy Docker container with database
> To get started with Docker read [Docker guide](https://docs.docker.com/get-started/)

1. Get the Postgres Docker Image

`docker pull postgres`

2. Create a directory to serve as the local mount point for Postgres data files

`mkdir docker\volumes\postgres`

3. Start container with Postgres database

`docker run -d --name <container-name> -e POSTGRES_PASSWORD=<pass> -d -p 5432:5432 --mount source=<volume-name>,target=/var/lib/postgresql/data postgres`

4. Restore your local database *diary* as described in *How to prepeare your local database* section
