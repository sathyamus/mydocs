# Running a PostgreSQL Database on Linux

The below steps describes how to set up a PostgreSQL database on Amazon Linux distribution.

### 1. Launching Amazon Linux AMI

### 2. Install PostgreSQL
```bash
sudo yum install postgresql postgresql-server postgresql-devel postgresql-contrib postgresql-docs
```
```
Loaded plugins: priorities, update-motd, upgrade-helper
Resolving Dependencies
--> Running transaction check
---> Package postgresql92.x86_64 0:9.2.24-2.66.amzn1 will be installed
--> Processing Dependency: postgresql92-libs(x86-64) = 9.2.24-2.66.amzn1 for package: postgresql92-9.2.24-2.66.amzn1.x86_64
--> Processing Dependency: libpq.so.5()(64bit) for package: postgresql92-9.2.24-2.66.amzn1.x86_64
---> Package postgresql92-contrib.x86_64 0:9.2.24-2.66.amzn1 will be installed
--> Processing Dependency: libossp-uuid.so.16()(64bit) for package: postgresql92-contrib-9.2.24-2.66.amzn1.x86_64
---> Package postgresql92-devel.x86_64 0:9.2.24-2.66.amzn1 will be installed
---> Package postgresql92-docs.x86_64 0:9.2.24-2.66.amzn1 will be installed
---> Package postgresql92-server-compat.x86_64 0:9.2.24-2.66.amzn1 will be installed
--> Processing Dependency: postgresql92-server(x86-64) = 9.2.24-2.66.amzn1 for package: postgresql92-server-compat-9.2.24-2.66.amzn1.x86_64
--> Running transaction check
---> Package postgresql92-libs.x86_64 0:9.2.24-2.66.amzn1 will be installed
---> Package postgresql92-server.x86_64 0:9.2.24-2.66.amzn1 will be installed
---> Package uuid.x86_64 0:1.6.2-27.22.amzn1 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

========================================================================================================================================================================
 Package                                            Arch                           Version                                   Repository                            Size
========================================================================================================================================================================
Installing:
 postgresql92                                       x86_64                         9.2.24-2.66.amzn1                         amzn-updates                         4.1 M
 postgresql92-contrib                               x86_64                         9.2.24-2.66.amzn1                         amzn-updates                         586 k
 postgresql92-devel                                 x86_64                         9.2.24-2.66.amzn1                         amzn-updates                         1.1 M
 postgresql92-docs                                  x86_64                         9.2.24-2.66.amzn1                         amzn-updates                          53 k
 postgresql92-server-compat                         x86_64                         9.2.24-2.66.amzn1                         amzn-updates                          39 k
Installing for dependencies:
 postgresql92-libs                                  x86_64                         9.2.24-2.66.amzn1                         amzn-updates                         261 k
 postgresql92-server                                x86_64                         9.2.24-2.66.amzn1                         amzn-updates                         6.0 M
 uuid                                               x86_64                         1.6.2-27.22.amzn1                         amzn-main                             58 k

Transaction Summary
========================================================================================================================================================================
Install  5 Packages (+3 Dependent packages)

Total download size: 12 M
Installed size: 38 M
Is this ok [y/d/N]: y
Downloading packages:
(1/8): postgresql92-devel-9.2.24-2.66.amzn1.x86_64.rpm                                                                                           | 1.1 MB  00:00:00
(2/8): postgresql92-docs-9.2.24-2.66.amzn1.x86_64.rpm                                                                                            |  53 kB  00:00:00
(3/8): postgresql92-9.2.24-2.66.amzn1.x86_64.rpm                                                                                                 | 4.1 MB  00:00:00
(4/8): postgresql92-contrib-9.2.24-2.66.amzn1.x86_64.rpm                                                                                         | 586 kB  00:00:00
(5/8): postgresql92-server-compat-9.2.24-2.66.amzn1.x86_64.rpm                                                                                   |  39 kB  00:00:00
(6/8): uuid-1.6.2-27.22.amzn1.x86_64.rpm                                                                                                         |  58 kB  00:00:00
(7/8): postgresql92-libs-9.2.24-2.66.amzn1.x86_64.rpm                                                                                            | 261 kB  00:00:00
(8/8): postgresql92-server-9.2.24-2.66.amzn1.x86_64.rpm                                                                                          | 6.0 MB  00:00:00
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                   9.0 MB/s |  12 MB  00:00:01
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : postgresql92-libs-9.2.24-2.66.amzn1.x86_64                                                                                                           1/8
  Installing : postgresql92-9.2.24-2.66.amzn1.x86_64                                                                                                                2/8
  Installing : postgresql92-server-9.2.24-2.66.amzn1.x86_64                                                                                                         3/8
  Installing : uuid-1.6.2-27.22.amzn1.x86_64                                                                                                                        4/8
  Installing : postgresql92-contrib-9.2.24-2.66.amzn1.x86_64                                                                                                        5/8
  Installing : postgresql92-server-compat-9.2.24-2.66.amzn1.x86_64                                                                                                  6/8
  Installing : postgresql92-docs-9.2.24-2.66.amzn1.x86_64                                                                                                           7/8
  Installing : postgresql92-devel-9.2.24-2.66.amzn1.x86_64                                                                                                          8/8
  Verifying  : postgresql92-libs-9.2.24-2.66.amzn1.x86_64                                                                                                           1/8
  Verifying  : uuid-1.6.2-27.22.amzn1.x86_64                                                                                                                        2/8
  Verifying  : postgresql92-contrib-9.2.24-2.66.amzn1.x86_64                                                                                                        3/8
  Verifying  : postgresql92-server-9.2.24-2.66.amzn1.x86_64                                                                                                         4/8
  Verifying  : postgresql92-docs-9.2.24-2.66.amzn1.x86_64                                                                                                           5/8
  Verifying  : postgresql92-server-compat-9.2.24-2.66.amzn1.x86_64                                                                                                  6/8
  Verifying  : postgresql92-devel-9.2.24-2.66.amzn1.x86_64                                                                                                          7/8
  Verifying  : postgresql92-9.2.24-2.66.amzn1.x86_64                                                                                                                8/8

Installed:
  postgresql92.x86_64 0:9.2.24-2.66.amzn1             postgresql92-contrib.x86_64 0:9.2.24-2.66.amzn1              postgresql92-devel.x86_64 0:9.2.24-2.66.amzn1
  postgresql92-docs.x86_64 0:9.2.24-2.66.amzn1        postgresql92-server-compat.x86_64 0:9.2.24-2.66.amzn1

Dependency Installed:
  postgresql92-libs.x86_64 0:9.2.24-2.66.amzn1               postgresql92-server.x86_64 0:9.2.24-2.66.amzn1               uuid.x86_64 0:1.6.2-27.22.amzn1

Complete!
```

### 3. Initializing PostgreSQL database
```
sudo service postgresql initdb
```
```
Initializing database:                                     [  OK  ]
```

### 4. Enabling remote connections (pg_hba.conf)
```
sudo vim /var/lib/pgsql9/data/pg_hba.conf
```
enable_remote_connections.PNG

### 5. Configuring port and Allowing remote connections (postgresql.conf)
```
sudo vim /var/lib/pgsql9/data/postgresql.conf
```
postgre_connections.PNG

### 6. Start the PostgreSQL service
```
sudo service postgresql start
```
```
Starting postgresql service:                               [  OK  ]
```

### 7. Login into PostgreSQL admin user
```
sudo su - postgres
psql -U postgres
```
```
psql (9.2.24)
Type "help" for help.
```

### 8. Setting up PostgreSQL admin user credentials
```
postgres=# ALTER USER postgres WITH PASSWORD 'postgres_password';
```
```
ALTER ROLE
```

### 9. Create Power users / applicative users like users with full / limited access (SUPERUSER, NOSUPERUSER)
```
postgres=# CREATE USER postgresdb SUPERUSER;
```
```
CREATE ROLE
```
```
postgres=# ALTER USER postgresdb WITH PASSWORD 'postgresdb_password';
```
```
ALTER ROLE
```

```
postgres=# CREATE USER appli_user NOSUPERUSER;
```
```
CREATE ROLE
```
```
postgres=# ALTER USER appli_user WITH PASSWORD 'appli_user_password';
```
```
ALTER ROLE
```

### 10. Creating a database and assocating OWNER account
```
CREATE DATABASE test_database WITH OWNER appli_user;
```
```

```

### 11. To Exit from Postgres (psql)
```
postgres-# \q
```

### 12. Verify Postgres service is running or not
```
-bash-4.2$ ps -ef | grep postgre
```

### 13. PostgreSQL installation and configuration is complete. Take the Public IP and using ppk / Console SSH, We can connect to database remotely.

### 14. Stop the PostgreSQL service
```
sudo service postgresql stop
```
