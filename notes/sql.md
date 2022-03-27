## SQL
* All `JOIN` can be considered as `CROSS JOIN` with filtering/constraints.
* When two tables has the same column as join constraint, we can use `USING`, e.g.
  ```SQL
  -- With ON subclause
  SELECT c.first_name, c.last_name, a.address
  FROM customer AS c INNER JOIN address AS a
  ON c.address_id = a.address_id;

  -- With USING subclause
  SELECT c.first_name, c.last_name, a.address
  FROM customer AS c INNER JOIN address AS a
  USING (address_id);
  ```
* `HAVING` is for aggregate, like `WHERE` for row data.
  ```SQL
  -- Error as WHERE is not aggregate filter
  SELECT fa.actor_id, f.rating, count(*)
    FROM film_actor AS fa INNER JOIN film AS f
    USING (film_id)
  WHERE f.rating IN ('G','PG')
    AND count(*) > 9                   -- ERROR, filtering aggregate in WHERE subclause
  GROUP BY fa.actor_id, f.rating;

  -- Using aggregate filter
  SELECT fa.actor_id, f.rating, count(*)
    FROM film_actor AS fa INNER JOIN film AS f
    USING (film_id)
  WHERE f.rating IN ('G','PG')
  GROUP BY fa.actor_id, f.rating
  HAVING count(*) > 9;                 -- HAVING is applicable for aggregate
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