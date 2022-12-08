## Trigger(https://dev.mysql.com/doc/refman/8.0/en/trigger-syntax.html)

To create a trigger or drop a trigger, use the [`CREATE TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "13.1.22 CREATE TRIGGER Statement") or [`DROP TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/drop-trigger.html "13.1.34 DROP TRIGGER Statement") statement, described in [Section 13.1.22, “CREATE TRIGGER Statement”](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "13.1.22 CREATE TRIGGER Statement"), and [Section 13.1.34, “DROP TRIGGER Statement”](https://dev.mysql.com/doc/refman/8.0/en/drop-trigger.html "13.1.34 DROP TRIGGER Statement").

Here is a simple example that associates a trigger with a table, to activate for [`INSERT`](https://dev.mysql.com/doc/refman/8.0/en/insert.html "13.2.6 INSERT Statement") operations. The trigger acts as an accumulator, summing the values inserted into one of the columns of the table.

```sql
mysql> CREATE TABLE account (acct_num INT, amount DECIMAL(10,2));
Query OK, 0 rows affected (0.03 sec)

mysql> CREATE TRIGGER ins_sum BEFORE INSERT ON account
       FOR EACH ROW SET @sum = @sum + NEW.amount;
Query OK, 0 rows affected (0.01 sec)
```

The [`CREATE TRIGGER`](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html "13.1.22 CREATE TRIGGER Statement") statement creates a trigger named `ins_sum` that is associated with the `account` table. It also includes clauses that specify the trigger action time, the triggering event, and what to do when the trigger activates:

**Examples :**

```sql
DELIMITER $$

CREATE TRIGGER must_be_adult
     BEFORE INSERT ON users FOR EACH ROW
     BEGIN
          IF NEW.age < 18
          THEN
              SIGNAL SQLSTATE '45000'
                    SET MESSAGE_TEXT = 'Must be an adult!';
          END IF;
     END;
$$

DELIMITER ;
```

```sql
DELIMITER $$

CREATE TRIGGER capture_unfollow
    AFTER DELETE ON users FOR EACH ROW
    BEGIN 
        INSERT INTO unfollow
        SET username = OLD.username;
END$$

DELIMITER ;
```