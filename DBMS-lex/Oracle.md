
By default, Oracle identifiers (table names, column names, etc.) are case-**insensitive**. You can make them case-sensitive by using quotes around them (eg: `SELECT * FROM "My_Table" WHERE "my_field" = 1`). SQL keywords (`SELECT`, `WHERE`, `JOIN`, etc.) are always case-insensitive.

On the other hand, string comparisons are case-**sensitive** (eg: `WHERE field='STRING'` will only match columns where it's `'STRING'`) by default. You can make them case-insensitive by setting `NLS_COMP` and `NLS_SORT` to the appropriate values (eg: `LINGUISTIC` and `BINARY_CI`, respectively).

> Note: When inquiring data dictionary views (eg: `dba_tables`) the names will be in upper-case if you created them without quotes, and the string comparison rules as explained in the second paragraph will apply here.

Some databases (Oracle, IBM DB2, PostgreSQL, etc.) will perform case-sensitive string comparisons by default, others case-insensitive (SQL Server, MySQL, SQLite). This isn't standard by any means, so just be aware of what your db settings are.