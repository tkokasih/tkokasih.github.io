## SQL
* All `JOIN` can be considered as `CROSS JOIN` with filtering!
* CTE is only introduced with MySQL 8.0, otherwise, we need to use Subquery, derived table, or temporary table, among other things.

## DB Dump and Reloading
* Dumping can be done with `mysqldump` (separate utility than mysql client)
  ```bash
  mysqldump -h {host} -u {user} -p --no-tablespaces {database} {table} | gzip > dbdump.sql.gz
  ```
  `gzip` for saving space which can be omitted.
  ```bash
  mysqldump -h {host} -u {user} -p --no-tablespaces {database} {table} > dbdump.sql
  ```

* Re-loading the dump can be done with:
  ```bash
  gunzip -c dbdump.sql.gz | mysql -h {host} -u {user} -p {database}
  ```

  Or if not from gzip
  ```bash
  mysql -h {host} -u {user} -p {database} < dbdump.sql.gz
  ```

* All above will prompt for password. The following variant is **NOT** safe, as the password is exposed:
  ```bash
  mysql -h {host} -u {user} -p{password}
  ```

  Why not safe? because the password will be in the command history, ps, proc, ...

* Other variant is to use options/config file (`~/.my.cnf`), but I haven't explored yet.