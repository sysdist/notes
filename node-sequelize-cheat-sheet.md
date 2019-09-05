##Sequelize notes - ORM for Sqlite3, PostgreSql, MySQL and other

Install node packages:
```bash
npm install --save express body-parser sequelize sequelize-cli sqlite3 nodemon
```

Init dir structure:
```bash
node_modules/.bin/sequelize init
```

Create model and migration:
```bash
node_modules/.bin/sequelize model:generate --name Contact --attributes firstName:string,lastName:string,phone:string,email:string
```

Check the db:
```bash
$ sqlite3 database.sqlite3
SQLite version 3.20.1 2017-08-24 16:21:36
Enter ".help" for usage hints.
sqlite> .schema
CREATE TABLE `SequelizeMeta` (`name` VARCHAR(255) NOT NULL UNIQUE PRIMARY KEY);
CREATE TABLE `Contacts` (`id` INTEGER PRIMARY KEY AUTOINCREMENT, `firstName` VARCHAR(255), `lastName` VARCHAR(255), `phone` VARCHAR(255), `email` VARCHAR(255), `createdAt` DATETIME NOT NULL, `updatedAt` DATETIME NOT NULL);
CREATE TABLE sqlite_sequence(name,seq);
```

Seed the db:
```bash
node_modules/.bin/sequelize db:seed:all
```

