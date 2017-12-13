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

---
