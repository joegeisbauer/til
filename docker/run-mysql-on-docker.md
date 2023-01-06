# Run MySQL Commands on Docker

There is a `docker exec` function that allows you to execute command line arguments on your docker machine from your local computer. This can be used in the following way to restore a database backup and/or run a sql script on the database. I am not learning this today, but I just wanted to document it as I use it from time to time.

## Restore database backup/Run MySQL Script.
```
cat <path-to-backup-or-sql-script> | docker exec -i <container-name> /usr/bin/mysql -u <user> --password=<password> <database>
```
