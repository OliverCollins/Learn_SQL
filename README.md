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
