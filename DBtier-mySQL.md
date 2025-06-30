# MySQL

Developer has chosen the database MySQL. Hence, we are trying to install it up and configure it.

**developer will tell DevOps engineer that which Versions of the DB Software is used,as a DevOps engineer we have to install that version in DB server**

***1.Before installing any version,we have to disable older version.***
```
sudo dnf remove mysql* -y
```
**dnf**   It is the package manager for RHEL-based Linux distributions,Used to install, update, remove, and manage software packages.

**-y**     Stands for "yes to all prompts"

***2.now install mySQL***
```
dnf install mysql-server -y
```

***3.We need to change the default root password in order to start using the database service.***

```
mysql_secure_installation --set-root-pass ExpenseApp@1
```

## Verification

We can check data by using client package called mysql.

Usually command to connect mysql server is

```
mysql -h <host-address> -u root -p<password>
```

But if your client and server both are in a single server, you can simply issue.

```
mysql
```

Once you got mysql prompt, you can use below command to check schemas/databases exist.

```
show databases;
```

Once you are in particular schema, you can get the list of tables.

```
show tables;
```

You can get entries of a table using

```
select * from <table_name>;
```
