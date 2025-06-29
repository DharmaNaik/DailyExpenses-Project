# MySQL

Developer has chosen the database MySQL. Hence, we are trying to install it up and configure it.

**developer will tell DevOps engineer that which Versions of the DB Software is used,as a DevOps engineer we have to install that version in DB server**
Before installing any version,we have to disable older version.below command will disables the default MySQL module stream that comes with your RHEL-based system (like CentOS, AlmaLinux, Rocky Linux).
```
dnf module disable mysql -y
```
Above command Explanation:
dnf    It is the package manager for RHEL-based Linux distributions,Used to install, update, remove, and manage software packages.
-y     Stands for "yes to all prompts"
module It's used when a package like MySQL, PHP, or Node.js has more than one version.

Here developer opted mySQL 8.0 Version.so we have to enable 8.0 version.below command will 

```
dnf module enable mysql:8.0 -y
```

now install mySQL
```
systemctl start mysqld
```
mysqld    is the process for the main daemon for the MySQL database server.

Next, We need to change the default root password in order to start using the database service. Use password ExpenseApp@1 or any other as per your choice.

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
