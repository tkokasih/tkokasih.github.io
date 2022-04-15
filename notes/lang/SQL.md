## Background

When dealing with SQL, sometimes I have to re-read the concept of JOIN and AGGREGATE.

This note is to shorten these refresh.

## SQL
* All `JOIN` can be considered as `CROSS JOIN` with filtering/constraints.
* When two tables has the same column as join constraint, we can use `USING`, e.g.
  ```SQL
  SELECT c.first_name, c.last_name, a.address
  FROM customer AS c INNER JOIN address AS a

  -- Using ON clause
  ON c.address_id = a.address_id;

  -- Using USING clause
  USING (address_id);
  ```
* `HAVING` is for aggregate, like `WHERE` for row data.
  ```SQL
  -- Error as WHERE is not aggregate filter
  SELECT fa.actor_id, f.rating, count(*)
    FROM film_actor AS fa INNER JOIN film AS f
    USING (film_id)

  -- ERROR as it tries to filter Aggregate function in WHERE clause
  WHERE f.rating IN ('G','PG')
    AND count(*) > 9
  GROUP BY fa.actor_id, f.rating;

  -- OK as it filter aggregate function in HAVING clause
  WHERE f.rating IN ('G','PG')
  GROUP BY fa.actor_id, f.rating
  HAVING count(*) > 9;
  ```
* CTE is only introduced with MySQL 8.0, otherwise, we need to use Subquery, derived table, or temporary table, among other things.

## DB Dump and Reloading
* Dumping can be done with `mysqldump` (separate utility than mysql client)
  ```bash
  # dumping db
  mysqldump -h {host} -u {user} -p --no-tablespaces {database} {table} | gzip > dbdump.sql.gz

  # reloading dump
  gunzip -c dbdump.sql.gz | mysql -h {host} -u {user} -p {database}
  ```
  Or without `gzip`
  ```bash
  # dumping db
  mysqldump -h {host} -u {user} -p --no-tablespaces {database} {table} > dbdump.sql

  # reloading dump
  mysql -h {host} -u {user} -p {database} < dbdump.sql.gz
  ```
* All above will prompt for password. The following variant is **NOT** safe, as the password is exposed:
  ```bash
  mysql -h {host} -u {user} -p{password}
  ```
  Why not safe? because the password will be in the command history, ps, proc, ...
* Other variant is to use options/config file (`~/.my.cnf`), but I haven't explored yet.