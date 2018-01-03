### SELECT Command

---

Arguably the most used command in SQL, SELECT is a good way to grab information from tables.

Here we have a table called: "Login"

| Username      | Password      | Email                       |
| ------------- | ------------- | --------------------------- |
| olivercollins | mypassword    | oliver.collins@colorado.edu |
| sqllover10    | selectiscool  | ilovesql@yahoo.com          |
| abc123        | password123   | myemail@aol.com             |

If we run the following code:

```sql
SELECT Username FROM Login;
```
The Usernames from the Login table will be returned.

| Username      |
| ------------- |
| olivercollins |
| sqllover10    |
| abc123        |

We can also select multiple columns just by adding columns to the SELECT command.

```sql
SELECT Username, Email FROM Login;
```

| Username      | Email                       |
| ------------- | --------------------------- |
| olivercollins | oliver.collins@colorado.edu |
| sqllover10    | ilovesql@yahoo.com          |
| abc123        | myemail@aol.com             |

Or you can select all columns with the * command.

```sql
SELECT * FROM Login;
```

| Username      | Password      | Email                       |
| ------------- | ------------- | --------------------------- |
| olivercollins | mypassword    | oliver.collins@colorado.edu |
| sqllover10    | selectiscool  | ilovesql@yahoo.com          |
| abc123        | password123   | myemail@aol.com             |

---

### WHERE Command

Let's create a new table:

Row | Username      | Password      | Email                       |
--- | ------------- | ------------- | --------------------------- |
1   | olivercollins | mypassword    | oliver.collins@colorado.edu |
2   | sqllover10    | selectiscool  | ilovesql@yahoo.com          |
3   | abc123        | password123   | myemail@aol.com             |


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

In both of these cases, we will see the first row returned.

---

### JOIN Command

---

### DELETE Command

With the DELETE clause, you can delete certain records from a table.

Row | Username      | Password      | Email                       |
--- | ------------- | ------------- | --------------------------- |
1   | olivercollins | mypassword    | oliver.collins@colorado.edu |
2   | sqllover10    | selectiscool  | ilovesql@yahoo.com          |
3   | abc123        | password123   | myemail@aol.com             |

From this table if we use the command:

```sql
DELETE FROM Login
WHERE Row=2;
```

Our new table would be

Row | Username      | Password      | Email                       |
--- | ------------- | ------------- | --------------------------- |
1   | olivercollins | mypassword    | oliver.collins@colorado.edu |
3   | abc123        | password123   | myemail@aol.com             |


You can also delete an entire table without deleting the structure (i.e. attributes or indexes):

```sql
DELETE FROM Login;
```

or

```sql
DELETE * FROM Login;
```

---
