# SQL

Structured Query Language (SQL) is a programming language used for manipulating data within a relational database management system. 

# Table of Contents
1. [SELECT Command](#select-command)
2. [WHERE Command](#where-command)
3. [COUNT Command](#count-command)
4. [AVG Command](#avg-command)
5. [SUM Command](#sum-command)
6. [JOIN Command](#join-command)
    1. [INNER Join](#join1)
    2. [RIGHT Join](#join2)
    3. [LEFT Join](#join3)
    4. [FULL Join](#join4)
7. [DELETE Command](#delete-command)
8. [UPDATE Command](#update-command)
9. [CREATE Command](#create-command)
10. [LIKE Command](#like-command)

### SELECT Command

---

Arguably the most used command in SQL, SELECT is a good way to grab information from tables.

Here we have a table called: "Login"

| Username      | Password      | Email                       |
| ------------- | ------------- | --------------------------- |
| olivercollins | mypassword    | oliver.collins@colorado.edu |
| timthecook    | selectiscool  | tim.cook@apple.com          |
| markymark     | password123   | mark.zuck@fb.com            |

If we run the following code:

```sql
SELECT Username FROM Login;
```

The Usernames from the Login table will be returned.

| Username      |
| ------------- |
| olivercollins |
| timthecook    |
| markymark     |

We can also select multiple columns just by adding columns to the SELECT command.

```sql
SELECT Username, Email FROM Login;
```

| Username      | Email                       |
| ------------- | --------------------------- |
| olivercollins | oliver.collins@colorado.edu |
| timthecook    | tim.cook@apple.com          |
| markymark     | mark.zuck@fb.com            |

Or you can select all columns with the * command.

```sql
SELECT * FROM Login;
```

| Username      | Password      | Email                       |
| ------------- | ------------- | --------------------------- |
| olivercollins | mypassword    | oliver.collins@colorado.edu |
| timthecook    | selectiscool  | tim.cook@apple.com          |
| markymark     | password123   | mark.zuck@fb.com            |

---

### WHERE Command

Let's create a new table:

Row | Username      | Password      | Email                       |
--- | ------------- | ------------- | --------------------------- |
1   | olivercollins | mypassword    | oliver.collins@colorado.edu |
2   | timthecook    | selectiscool  | tim.cook@apple.com          |
3   | markymark     | password123   | mark.zuck@fb.com            |


With the WHERE clause, you can select certain aspects of a table.

```sql
SELECT * FROM Login
WHERE Password='mypassword';
```
You can also use WHERE numerically

```sql
SELECT * FROM Login
WHERE Row=1;
```

In both of these cases, we will see:

Row | Username      | Password      | Email                       |
--- | ------------- | ------------- | --------------------------- |
1   | olivercollins | mypassword    | oliver.collins@colorado.edu |

---

### COUNT command

Count is very similar to length in many other programming languages. It simply counts the number of rows in a particular column.

```sql
SELECT COUNT(*)
FROM Login;
```

### AVG command

To be added...

### SUM command

To be added...

---

### JOIN Command

#### Inner Join <a name="join1"></a>

Login Table

Row | Username      | Password      | Email                       |
--- | ------------- | ------------- | --------------------------- |
1   | olivercollins | mypassword    | oliver.collins@colorado.edu |
2   | timthecook    | selectiscool  | tim.cook@apple.com          |
3   | markymark     | password123   | mark.zuck@fb.com            |

Item Table

UserID | ItemNumber    | Country       | Email                       |
---    | ------------- | ------------- | --------------------------- |
1      | 20938         | China         | oliver.collins@colorado.edu |
2      | 19922         | South Korea   | tim.cook@apple.com          |
3      | 98472         | China         | mark.zuck@fb.com            |

```sql
SELECT Login.Username, Item.UserID
FROM Login
INNER JOIN Item ON Login.Email = Item.Email
```

#### Right Join <a name="join2"></a>

```sql
SELECT Login.Username, Item.Country
FROM Login
RIGHT JOIN Item ON Login.Email = Item.Email
```

#### Left Join <a name="join3"></a>

#### Full Join <a name="join4"></a>

---

### DELETE Command

With the DELETE clause, you can delete certain records from a table.

Row | Username      | Password      | Email                       |
--- | ------------- | ------------- | --------------------------- |
1   | olivercollins | mypassword    | oliver.collins@colorado.edu |
2   | timthecook    | selectiscool  | tim.cook@apple.com          |
3   | markymark     | password123   | mark.zuck@fb.com            |

From this table if we use the command:

```sql
DELETE FROM Login
WHERE Row=2;
```

Our new table would be

Row | Username      | Password      | Email                       |
--- | ------------- | ------------- | --------------------------- |
1   | olivercollins | mypassword    | oliver.collins@colorado.edu |
3   | markymark     | password123   | mark.zuck@fb.com            |


You can also delete an entire table without deleting the structure (i.e. attributes or indexes):

```sql
DELETE FROM Login;
```

or

```sql
DELETE * FROM Login;
```

---

### UPDATE Command

You can use the UPDATE clause to modify data within a table

Row | Username      | Password      | Email                       |
--- | ------------- | ------------- | --------------------------- |
1   | olivercollins | mypassword    | oliver.collins@colorado.edu |
2   | timthecook    | selectiscool  | tim.cook@apple.com          |
3   | markymark     | password123   | mark.zuck@fb.com            |

```sql
UPDATE Login
SET Username = 'new_username', Email= 'new_username@yahoo.com'
WHERE Row = 1;
```

Our modified table would now look like:

Row | Username      | Password      | Email                       |
--- | ------------- | ------------- | --------------------------- |
1   | new_username  | mypassword    | new_username@yahoo.com      |
2   | timthecook    | selectiscool  | tim.cook@apple.com          |
3   | markymark     | password123   | mark.zuck@fb.com            |

---

### CREATE command

Creating a table in SQL is easy. Let's say you wanted to create an empty Login table.

```sql
CREATE TABLE Login (
    Row int,
    Username varchar(255),
    Password varchar(255),
    Email varchar(255),
);
```

### LIKE command

```sql
SELECT * FROM Login
WHERE Username LIKE 'a%';
```
