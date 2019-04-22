## DATABASE UTILITIES

#### set source
Define the source for creation & retrieval of databases
```sh
lazlo => set source C://Users/Public/Project
```
#### Note : In windows pass the source in a Drive://dir/subdir format. In linux & mac you may follow the normal notation. Also keep in mind that you must have write permissions for the source.

#### source
Displays the current data source
```sh
lazlo => source
```

#### newdb / create db
Creates a new database
```sh
lazlo => newdb mydb
```
```sh
lazlo => create db mydb
```

#### list db
Lists all the databases within the current data source
```sh
lazlo => list db
```

#### db / select
Select a database for further operations
```sh
lazlo => db mydb
```
```sh
lazlo => select mydb
```

#### track
Tell lazlo that a folder is a valid database. This operation is useful when the database was not created on the local machine or when the data source was changed
```sh
lazlo => track mydb
```

#### untrack
Stop tracking a database. This turns the database into a normal folder which is no longer recognized by lazlo. On changing the data source, all databases are untracked as the inbuilt db_tracker is cleared. Re-track them using track command
```sh
lazlo => untrack mydb
```

#### drop / delete db
Delete a database permanently
```sh
lazlo => drop mydb
```
```sh
lazlo => delete db mydb
```