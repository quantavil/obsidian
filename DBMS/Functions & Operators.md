- [[#[Operator](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html)|Operator]]
	- [[#[Operator](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html)#SQL Arithmetic Operators|SQL Arithmetic Operators]]
	- [[#[Operator](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html)#SQL Comparison Operators|SQL Comparison Operators]]
	- [[#[Operator](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html)#SQL Logical Operators|SQL Logical Operators]]
- [[#[Flow Control Functions](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html)|Flow Control Functions]]
	- [[#[Flow Control Functions](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html)#Case Operator|Case Operator]]
	- [[#[Flow Control Functions](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html)#IF|IF]]
	- [[#[Flow Control Functions](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html)#IFNULL|IFNULL]]
	- [[#[Flow Control Functions](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html)#NULLIF|NULLIF]]
- [[#[Numeric Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html)|Numeric Functions and Operators]]
- [[#[Date and Time Functions](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html)|Date and Time Functions]]
	- [[#[Date and Time Functions](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html)#[Temporal Intervals](https://dev.mysql.com/doc/refman/8.0/en/expressions.html#temporal-intervals)|Temporal Intervals]]
		- [[#[Temporal Intervals](https://dev.mysql.com/doc/refman/8.0/en/expressions.html#temporal-intervals)#Automatic Initialization and Updating for TIMESTAMP and DATETIME|Automatic Initialization and Updating for TIMESTAMP and DATETIME]]
- [[#[String Functions](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html)|String Functions]]
- [[#[Cast Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html)|Cast Functions and Operators]]
	- [[#[Cast Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html)#Cast|Cast]]
	- [[#[Cast Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html)#Convert|Convert]]
- [[#[Aggregate Function](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions-and-modifiers.html)|Aggregate Function]]
- [[#[Window Functions](https://dev.mysql.com/doc/refman/8.0/en/window-functions.html)|Window Functions]]


## [Operator](https://dev.mysql.com/doc/refman/8.0/en/non-typed-operators.html)

An operator is a reserved word or a character used primarily in an SQL statement's WHERE clause to perform operation(s), such as comparisons and arithmetic operations.

-   Arithmetic operators
-   Comparison operators
-   Logical operators
-   Operators used to negate conditions

### SQL Arithmetic Operators

Assume **'variable a'** holds 10 and **'variable b'** holds 20, then − [Show Examples](https://www.tutorialspoint.com/sql/sql-arithmetic-operators.htm)

| Operator | Description | Example |
| --- | --- | --- |
| \+ (Addition) | Adds values on either side of the operator. | a + b will give 30 |
| \- (Subtraction) | Subtracts right hand operand from left hand operand. | a - b will give -10 |
| \* (Multiplication) | Multiplies values on either side of the operator. | a \* b will give 200 |
| / (Division) | Divides left hand operand by right hand operand. | b / a will give 2 |
| % (Modulus) | Divides left hand operand by right hand operand and returns remainder. | b % a will give 0 |

### SQL Comparison Operators

Assume **'variable a'** holds 10 and **'variable b'** holds 20, then − [Show Examples](https://www.tutorialspoint.com/sql/sql-comparison-operators.htm)

| Operator | Description | Example |
| --- | --- | --- |
| \= | Checks if the values of two operands are equal or not, if yes then condition becomes true. | (a = b) is not true. |
| != | Checks if the values of two operands are equal or not, if values are not equal then condition becomes true. | (a != b) is true. |
| <> | Checks if the values of two operands are equal or not, if values are not equal then condition becomes true. | (a <> b) is true. |
| \> | Checks if the value of left operand is greater than the value of right operand, if yes then condition becomes true. | (a > b) is not true. |
| < | Checks if the value of left operand is less than the value of right operand, if yes then condition becomes true. | (a < b) is true. |
| \>= | Checks if the value of left operand is greater than or equal to the value of right operand, if yes then condition becomes true. | (a >= b) is not true. |
| <= | Checks if the value of left operand is less than or equal to the value of right operand, if yes then condition becomes true. | (a <= b) is true. |
| !< | Checks if the value of left operand is not less than the value of right operand, if yes then condition becomes true. | (a !< b) is false. |
| !> | Checks if the value of left operand is not greater than the value of right operand, if yes then condition becomes true. | (a !> b) is true. |


### SQL Logical Operators

Here is a list of all the logical operators available in SQL. [Show Examples](https://www.tutorialspoint.com/sql/sql-logical-operators.htm)

| Sr.No. | Operator                  | Description                                                                                                                       |
| ------ | ------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| 1      | **[[Operators#AND]]**     | The AND operator allows the existence of multiple conditions in an SQL statement's WHERE clause.                                  |
| 2      | **[[Operators#OR]]** | The OR operator is used to combine multiple conditions in an SQL statement's WHERE clause.|
| 3      |  **[[Operators#NOT]]** |The NOT operator reverses the meaning of the logical operator with which it is used. Eg: NOT EXISTS, NOT BETWEEN, NOT IN, etc. **This is a negate operator.** |
| 4      | **[[Operators#BETWEEN]]** | The BETWEEN operator is used to search for values that are within a set of values, given the minimum value and the maximum value. |
| 5      | **[[Operators#IN]]**      | The IN operator is used to compare a value to a list of literal values that have been specified.                                  |
| 6      | **[[Operators#LIKE]]**    | The LIKE operator is used to compare a value to similar values using wildcard operators.                                          |
| 7      | **[[Operators#ALL]]**     | The ALL operator is used to compare a value to all values in another value set.                                                   |
| 8      | **[[Operators#ANY]]**     | The ANY operator is used to compare a value to any applicable value in the list as per the condition.                             |
| 9      | **[[Operators#EXISTS]]**  | The EXISTS operator is used to search for the presence of a row in a specified table that meets a certain criterion.              |
| 10     | **[[Operators#UNION]]** |The UNIQUE operator searches every row of a specified table for uniqueness (no duplicates).|
| 11    | **[[Operators#IS NULL]]** |The NULL operator is used to compare a value with a NULL value.|

---

## [Flow Control Functions](https://dev.mysql.com/doc/refman/8.0/en/flow-control-functions.html)

| Name | Description |
| --- | --- |
| [`CASE`](https://dev.mysql.com/doc/refman/5.7/en/flow-control-functions.html#operator_case) | Case operator |
| [`IF()`](https://dev.mysql.com/doc/refman/5.7/en/flow-control-functions.html#function_if) | If/else construct |
| [`IFNULL()`](https://dev.mysql.com/doc/refman/5.7/en/flow-control-functions.html#function_ifnull) | Null if/else construct |
| [`NULLIF()`](https://dev.mysql.com/doc/refman/5.7/en/flow-control-functions.html#function_nullif) | Return NULL if expr1 = expr2 |

### Case Operator

```sql
CASE value WHEN compare_value THEN result [WHEN compare_value THEN result ...] [ELSE result] END

CASE WHEN condition THEN result [WHEN condition THEN result ...] [ELSE result] END 
```

The first [`CASE`](https://dev.mysql.com/doc/refman/5.7/en/flow-control-functions.html#operator_case) syntax returns the _`result`_ for the first ``_`value`_=_`compare_value`_`` comparison that is true. The second syntax returns the result for the first condition that is true. If no comparison or condition is true, the result after `ELSE` is returned, or `NULL` if there is no `ELSE` part.

```sql
mysql> SELECT CASE 1 WHEN 1 THEN 'one'
    ->     WHEN 2 THEN 'two' ELSE 'more' END;
        -> 'one'
mysql> SELECT CASE WHEN 1>0 THEN 'true' ELSE 'false' END;
        -> 'true'
mysql> SELECT CASE BINARY 'B'
    ->     WHEN 'a' THEN 1 WHEN 'b' THEN 2 END;
        -> NULL
```

> [! Note ]
>  The [`CASE`](https://dev.mysql.com/doc/refman/5.7/en/case.html "13.6.5.1 CASE Statement") statement cannot have an `ELSE NULL` clause, and it is terminated with `END CASE` instead of `END`.


### IF 

```sql
IF(expr1,expr2,expr3)
```

If _`expr1`_ is `TRUE` i.e. (_`expr1`_ <> 0`` and ``_`expr1`_ IS NOT NULL`), IF() returns _`expr2`_. Otherwise, it returns _`expr3`_.

```sql
mysql> SELECT IF(1>2,2,3);
        -> 3
mysql> SELECT IF(1<2,'yes','no');
        -> 'yes'
mysql> SELECT IF(STRCMP('test','test1'),'no','yes');
        -> 'no'
```

> [! Note]
> There is also an [`IF`](https://dev.mysql.com/doc/refman/5.7/en/if.html "13.6.5.2 IF Statement") _statement_, which differs from the [`IF()`](https://dev.mysql.com/doc/refman/5.7/en/flow-control-functions.html#function_if) _function_ described here

### IFNULL
```sql
IFNULL(expr1,expr2)
```

If _`expr1`_ is not `NULL`, [`IFNULL()`](https://dev.mysql.com/doc/refman/5.7/en/flow-control-functions.html#function_ifnull) returns _`expr1`_; otherwise it returns _`expr2`_.

```sql
mysql> SELECT IFNULL(1,0);
        -> 1
mysql> SELECT IFNULL(NULL,10);
        -> 10
mysql> SELECT IFNULL(1/0,10);
        -> 10
mysql> SELECT IFNULL(1/0,'yes');
        -> 'yes'
```

### NULLIF

```sql
NULLIF(expr1,expr2)
```

Returns `NULL` if ``_`expr1`_ = _`expr2`_`` is true, otherwise returns _`expr1`_. This is the same as CASE WHEN _`expr1`_ = _`expr2`_ THEN NULL ELSE _`expr1`_ END

```sql
mysql> SELECT NULLIF(1,1);
        -> NULL
mysql> SELECT NULLIF(1,2);
        -> 1
```

---


## [Numeric Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html)

| S.No. | Name | Description |
| --- | --- | --- |
| 1 | [`ABS()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_abs) | Return the absolute value |
| 2 | [`CONV()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_conv) | Convert numbers between different number bases |
| 3 | [`DEGREES()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_degrees) | Convert radians to degrees |
| 4 | [`EXP()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_exp) | Raise to the power of |
| 5 | [`MOD()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_mod) | Return the remainder |
| 6 | [`POW()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_pow) | Return the argument raised to the specified power |
| 7 | [`POWER()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_power) | Return the argument raised to the specified power |
| 8 | [`RAND()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_rand) | Return a random floating-point value |
| 9 | [`ROUND()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_round) | Round the argument |
| 10 | [`SIGN()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_sign) | Return the sign of the argument |
| 11 | [`SQRT()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_sqrt) | Return the square root of the argument |
| 12 | [`TRUNCATE()`](https://dev.mysql.com/doc/refman/8.0/en/mathematical-functions.html#function_truncate) | Truncate to specified number of decimal places |

---


## [Date and Time Functions](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html)
| Function | Descriptions | Syntax | 
|  --- | --- | --- | 
| **CURDATE** *CURRENT_DATE* | The CURDATE() function returns the current date.  The date is returned as "YYYY-MM-DD" (string) or as YYYYMMDD (numeric). | `CURDATE()` |
| **CURTIME** or *CURRENT_TIME* | The CURTIME() function returns the current time. The time is returned as "HH-MM-SS" (string) or as HHMMSS.uuuuuu (numeric). |`CURTIME()`|
| **NOW** or *CURRENT_TIMESTAMP* | The NOW() function returns the current date and time. The date and time is returned as "YYYY-MM-DD HH-MM-SS" (string) or as YYYYMMDDHHMMSS.uuuuuu (numeric). | `NOW()` |
| **DATE_FORMAT** |	Format date as specified [Ref](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_date-format) | `DATE_FORMAT(_date_,_format_)` |
| **DATE_ADD , DATE_SUB** |	Add and Subtract time values (intervals) to a date value | `DATE_ADD(date,INTERVAL expr unit), DATE_SUB(date,INTERVAL expr unit)` |

### [Temporal Intervals](https://dev.mysql.com/doc/refman/8.0/en/expressions.html#temporal-intervals)

_`interval_expr`_ in expressions represents a temporal interval. Intervals have this syntax:

```sql
INTERVAL expr unit
```

_`expr`_ represents a quantity. _`unit`_ represents the unit for interpreting the quantity; it is a specifier such as `HOUR`, `DAY`, or `WEEK`. The `INTERVAL` keyword and the _`unit`_ specifier are not case-sensitive.

Temporal intervals are used for certain functions, such as [`DATE_ADD()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_date-add) and [`DATE_SUB()`](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_date-sub):

```sql
mysql> SELECT DATE_ADD('2018-05-01',INTERVAL 1 DAY);
        -> '2018-05-02'
mysql> SELECT DATE_SUB('2018-05-01',INTERVAL 1 YEAR);
        -> '2017-05-01'
```

Temporal arithmetic also can be performed in expressions using `INTERVAL` together with the [`+`](https://dev.mysql.com/doc/refman/8.0/en/arithmetic-functions.html#operator_plus) or [`-`](https://dev.mysql.com/doc/refman/8.0/en/arithmetic-functions.html#operator_minus) operator:

```sql
date + INTERVAL expr unit
date - INTERVAL expr unit
```

```sql
mysql> SELECT '2018-12-31 23:59:59' + INTERVAL 1 SECOND;
        -> '2019-01-01 00:00:00'
mysql> SELECT INTERVAL 1 DAY + '2018-12-31';
        -> '2019-01-01'
mysql> SELECT '2025-01-01' - INTERVAL 1 SECOND;
        -> '2024-12-31 23:59:59'
```

#### Automatic Initialization and Updating for TIMESTAMP and DATETIME

[`TIMESTAMP`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "11.2.2 The DATE, DATETIME, and TIMESTAMP Types") and [`DATETIME`](https://dev.mysql.com/doc/refman/8.0/en/datetime.html "11.2.2 The DATE, DATETIME, and TIMESTAMP Types") columns can be automatically initialized and updated to the current date and time (that is, the current timestamp).   [Ref](https://dev.mysql.com/doc/refman/8.0/en/timestamp-initialization.html#:~:text=An%20auto%2Dinitialized%20column%20is,changed%20from%20its%20current%20value.)

```mysql
CREATE TABLE t1 (   ts TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,   dt DATETIME DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP );
```

---


## [String Functions](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html)

| Function | Descriptions | Syntax | 
|  --- | --- | --- | 
| **CONCAT** | The CONCAT() function adds two or more expressions together. | `CONCAT(_expression1_, _expression2_, _expression3_,...)` | 
| **CONCAT_WS** | The CONCAT_WS() function adds two or more expressions together with a separator. | `CONCAT_WS(_separator_, _expression1_, _expression2_, _expression3_,...)` |
| **SUBSTRING** or *SUBSTR* or *MID* | The SUBSTRING() function extracts a substring from a string (starting at any position). | `SUBSTRING(_string_, _start_, _length_)`  or `SUBSTRING(_string_ FROM _start_ FOR _length_)` |
| **REPLACE** | The REPLACE() function replaces all occurrences of a substring within a string, with a new substring (case-sensitive replacement) | `REPLACE(_string_, _from_string_, _new_string_)` |
| **REVERSE** | The REVERSE() function reverses a string and returns the result. | `REVERSE(_string_)` |
| **CHAR_LENGTH** or *CHARACTER_LENGTH* | The CHAR_LENGTH() function return the length of a string (in characters). | `CHAR_LENGTH(_string_)` |
| **UPPER** or *UCASE* | The UPPER() function converts a string to upper-case. | `UPPER(_text_)` |
| **LOWER** or *LCASE* | The LOWER() function converts a string to lower-case. | `LOWER(_text_)` |

---


## [Cast Functions and Operators](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html)

| Name | Description |
| --- | --- |
| [`CAST()`](https://dev.mysql.com/doc/refman/5.7/en/cast-functions.html#function_cast) | Cast a value as a certain type |
| [`CONVERT()`](https://dev.mysql.com/doc/refman/5.7/en/cast-functions.html#function_convert) | Cast a value as a certain type |

**Parameter Values**

| Parameter | Description |
| --- | --- |
| _value_ | Required. The value to convert |
| _datatype_ | Required. The datatype to convert to. Can be one of the following:  
| Value | Description |
| --- | --- |
| DATE | Converts _value_ to DATE. Format: "YYYY-MM-DD" |
| DATETIME | Converts _value_ to DATETIME. Format: "YYYY-MM-DD HH:MM:SS" |
| DECIMAL | Converts _value_ to DECIMAL. Use the optional M and D parameters to specify the maximum number of digits (M) and the number of digits following the decimal point (D). |
| TIME | Converts _value_ to TIME. Format: "HH:MM:SS" |
| CHAR | Converts _value_ to CHAR (a fixed length string) |
| NCHAR | Converts _value_ to NCHAR (like CHAR, but produces a string with the national character set) |
| SIGNED | Converts _value_ to SIGNED (a signed 64-bit integer) |
| UNSIGNED | Converts _value_ to UNSIGNED (an unsigned 64-bit integer) |
| BINARY | Converts _value_ to BINARY (a binary string) |

### Cast

[CAST(_`expr`_ AS _type](https://dev.mysql.com/doc/refman/5.7/en/cast-functions.html#function_cast) takes an expression of any type and produces a result value of the specified type. This operation may also be expressed as [CONVERT(_`expr`_, _`type`_)](https://dev.mysql.com/doc/refman/5.7/en/cast-functions.html#function_convert), which is equivalent.

```sql
mysql> SELECT CAST(1 AS UNSIGNED) - 2.0;
        -> -1.0
mysql> CREATE TABLE new_table SELECT CAST('2000-01-01' AS DATE) AS c1;
mysql> SHOW CREATE TABLE new_table\G
*************************** 1. row ***************************
       Table: new_table
Create Table: CREATE TABLE `new_table` (
  `c1` date DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1
```

### Convert

[`CONVERT()`](https://dev.mysql.com/doc/refman/5.7/en/cast-functions.html#function_convert) with a `USING` clause converts data between character sets:

```sql
SELECT CONVERT('abc' USING utf8);
```

---


## [Aggregate Function](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions-and-modifiers.html) 

This section describes aggregate functions that operate on sets of values. They are often used with a `GROUP BY` clause to group values into subsets.


| Name | Description |
| --- | --- |
| [`AVG()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_avg) | Return the average value of the argument |
| [`COUNT()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count) | Return a count of the number of rows returned |
| [`COUNT(DISTINCT)`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_count-distinct) | Return the count of a number of different values |
| [`GROUP_CONCAT()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_group-concat) | Return a concatenated string |
| [`MAX()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_max) | Return the maximum value |
| [`MIN()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_min) | Return the minimum value |
| [`SUM()`](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html#function_sum) | Return the sum |

---


## [Window Functions](https://dev.mysql.com/doc/refman/8.0/en/window-functions.html)

This section describes nonaggregate window functions that, for each row from a query, perform a calculation using rows related to that row. Most aggregate functions also can be used as window functions;

| Name | Description |
| --- | --- |
| [`CUME_DIST()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function_cume-dist) | Cumulative distribution value |
| [`DENSE_RANK()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function_dense-rank) | Rank of current row within its partition, without gaps |
| [`FIRST_VALUE()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function_first-value) | Value of argument from first row of window frame |
| [`LAG()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function_lag) | Value of argument from row lagging current row within partition |
| [`LAST_VALUE()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function_last-value) | Value of argument from last row of window frame |
| [`LEAD()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function_lead) | Value of argument from row leading current row within partition |
| [`NTH_VALUE()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function_nth-value) | Value of argument from N-th row of window frame |
| [`NTILE()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function_ntile) | Bucket number of current row within its partition. |
| [`PERCENT_RANK()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function_percent-rank) | Percentage rank value |
| [`RANK()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function_rank) | Rank of current row within its partition, with gaps |
| [`ROW_NUMBER()`](https://dev.mysql.com/doc/refman/8.0/en/window-function-descriptions.html#function_row-number) | Number of current row within its partition |

---