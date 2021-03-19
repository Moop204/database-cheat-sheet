# database-cheat-sheet

Initialising Database with a File
After writing a .sql file call the file based on its absolute position 
```
psql -U [username] -f /location/to/file/init.sql
```

Dropping Databases 
Do this early if at all. 

If table is relied on by other tables (used as FK) then add CASCADE to delete those foreign keys as well. 
```
DROP TABLE IF EXISTS [table] CASCADE; 
```

Giving Permissions
Make a separate user to work on and only use the admin account for setup.
Enter a database and create a user.
```
CREATE USER [username] WITH PASSWORD [password];
```
Then give them permissions. Try to be as restrictive as possible. All database tables if not given a schema will be placed in the 'public' schema. 
```
GRANT ALL ON ALL TABLES IN SCHEMA public TO [username];
```
