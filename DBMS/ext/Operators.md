1. [[#AND|AND]]
2. [[#OR|OR]]
3. [[#NOT|NOT]]
4. [[#BETWEEN|BETWEEN]]
5. [[#IN|IN]]
6. [[#LIKE|LIKE]]
7. [[#ANY|ANY]]
8. [[#ALL|ALL]]
9. [[#EXISTS|EXISTS]]
10. [[#UNION|UNION]]
11. [[#IS NULL|IS NULL]]


## AND

The `AND` operator displays a record if all the conditions separated by `AND` are TRUE.

```mysql
SELECT _column1_, _column2, ..._  
FROM _table_name_  
WHERE _condition1_ AND _condition2_ AND _condition3 ..._;
```

## OR

The `OR` operator displays a record if any of the conditions separated by `OR` is TRUE.

```mysql
SELECT _column1_, _column2, ..._  
FROM _table_name_  
WHERE _condition1_ OR _condition2_ OR _condition3 ..._;
```

## NOT

The `NOT` operator displays a record if the condition(s) is NOT TRUE.

```mysql
SELECT _column1_, _column2, ..._  
FROM _table_name_  
WHERE NOT _condition_;
```

## BETWEEN 

The `BETWEEN` operator selects values within a given range. The values can be numbers, text, or dates. The `BETWEEN` operator is inclusive: begin and end values are included.

```mysql
SELECT _column_name(s)_  
FROM _table_name_  
WHERE _column_name_ BETWEEN _value1_ AND _value2;
```


**BETWEEN condition with date**

MySQL BETWEEN condition also facilitates you to retrieve records according to date.

```mysql
SELECT _column_name(s)_  
FROM _table_name_  
WHERE _column_name_ CAST ('yyyy-mm-dd' AS DATE) AND CAST ('yyyy-mm-dd' AS DATE);
```


## IN

The `IN` operator allows you to specify multiple values in a `WHERE` clause. The `IN` operator is a shorthand for multiple `OR` conditions.

```mysql
SELECT column_name(s)  
FROM table_name 
WHERE column_name IN (value1, value2, ...);
```

```mysql
SELECT _column_name(s)_  
FROM _table_name_  
WHERE _column_name_ IN (SELECT STATEMENT);
```
 
  
## LIKE 

The `LIKE` operator is used in a `WHERE` clause to search for a specified pattern in a column.
There are two wildcards often used in conjunction with the `LIKE` operator: 
-   The percent sign (%) represents zero, one, or multiple characters
-   The underscore sign (_) represents one, single character

The percent sign and the underscore can also be used in combinations!

A wildcard character is used to substitute one or more characters in a string.

Wildcard characters are used with the *LIKE* operator. The `LIKE` operator is used in a `WHERE` clause to search for a specified pattern in a column.

| LIKE Operator | Description |
| --- | --- |
| WHERE CustomerName LIKE 'a%' | Finds any values that start with "a" |
| WHERE CustomerName LIKE '%a' | Finds any values that end with "a" |
| WHERE CustomerName LIKE '%or%' | Finds any values that have "or" in any position |
| WHERE CustomerName LIKE '\_r%' | Finds any values that have "r" in the second position |
| WHERE CustomerName LIKE 'a\_%' | Finds any values that start with "a" and are at least 2 characters in length |
| WHERE CustomerName LIKE 'a\_\_%' | Finds any values that start with "a" and are at least 3 characters in length |
| WHERE ContactName LIKE 'a%o' | Finds any values that start with "a" and ends with "o" |
| WHERE CustomerName LIKE '%or%' | Finds any values that have "or" in any position |
| WHERE CustomerName LIKE 'a\_%\_%' | Finds any values that starts with "a" and are at least 3 characters in length |

## ANY

The `ANY` operator:

-   returns a boolean value as a result
-   returns TRUE if ANY of the subquery values meet the condition

`ANY` means that the condition will be true if the operation is true for any of the values in the range.

```mysql
SELECT _column_name(s)_  
FROM _table_name_  
WHERE _column_name operator_ ANY  
  (SELECT _column_name_  FROM _table_name_  WHERE _condition_);
```

## ALL

The `ALL` operator:

-   returns a Boolean value as a result
-   returns TRUE if ALL of the subquery values meet the condition
-   is used with `SELECT`, `WHERE` and `HAVING` statements

`ALL` means that the condition will be true only if the operation is true for all values in the range. 


```mysql
SELECT ALL _column_name(s)_  
FROM _table_name_  
WHERE _condition_;
```

```mysql
SELECT _column_name(s)_  
FROM _table_name_  
WHERE _column_name operator_ ALL  
  (SELECT _column_name_  FROM _table_name_  WHERE _condition_);
```


## EXISTS 

The `EXISTS` operator is used to test for the existence of any record in a subquery.
The `EXISTS` operator returns TRUE if the subquery returns one or more records.

```mysql
SELECT _column_name(s)_  
FROM _table_name_  
WHERE EXISTS  
(SELECT _column_name_ FROM _table_name_ WHERE _condition_);
```

## UNION 
The `UNION` operator is used to combine the result-set of two or more `SELECT` statements.

-   Every `SELECT` statement within `UNION` must have the same number of columns
-   The columns must also have similar data types
-   The columns in every `SELECT` statement must also be in the same order

```mysql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

```mysql
SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2;
```

## IS NULL

**Null Value** : A field with a NULL value is a field with no value.

**Note:** A NULL value is different from a zero value or a field that contains spaces. A field with a NULL value is one that has been left blank during record creation!

**IS NULL Syntax**

```SQL
SELECT _column_names  
_FROM _table_name_  
WHERE _column_name_ IS NULL;
```

**IS NOT NULL Syntax**

```SQL
SELECT _column_names  
_FROM _table_name_  
WHERE _column_name_ IS NOT NULL;
```

