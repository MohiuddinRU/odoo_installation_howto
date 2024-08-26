First install postgres

To login as postgres user run
```sudo -i -u postgres```
Now you are logged in as postgres user.


To run query to postgres, you need to type
```psql```
Now you entered into psql database qeury terminal.
You are ready to run any postgres query.

Now create an user with CREATEDB permission. 
```create user demoUser with password '1234'```

Here `1234` is the password of the user.

To change this password again run below query:
```alter user demoUser with password 'NewPassword'```

To give the user access to create database and login into postgres we can assign role like this
`alter user demoUser CREATEDB LOGIN`

Now to login with user demoUser and password run:
```psql --host localhost --port 5432 --username demoUser --password``` 

In case of password promt provide the password. Check if you now can create database;
