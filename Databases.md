# Databases

## Postgres
sudo apt update
sudo apt install postgresql postgresql-contrib

#### log into postgres
sudo -i -u postgres

#### get into interactive terminal
psql
createdb mydatabase
createuser myuser --superuser --pwprompt
```sql
ALTER USER postgres WITH PASSWORD 'newpassword';
```

#### connect to db
psql -d mydatabase

#### exit from psql command line
\q

#### logout postgres user shell
exit
