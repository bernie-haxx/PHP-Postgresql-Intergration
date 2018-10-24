L.A.P.P Intergration
==========================

![photo](https://cdn-images-1.medium.com/max/1000/1*Vb2C19KbtkmfD7XAMSAcPA.png)

# How to install Apache, PhP, Postgresql (LAPP) on Ubuntu 16.04

## Introduction

Welcome to an introduction on how to enable `L.A.P.P.`intergration to your local machine.

This documentation is based on starting up the `L.A.P.P.` package which is based on the following prerequisities:

### Prerequisities

+ Installing [PHP]()
+ Having a Linux Distribution like [Ubuntu]()
+ Installing [Apache2]()
+ Installing [PostgrSQL]() and [PHPpgAdmin]().

# Starting Up The Process

In one way or another, you will need to install a web server locally on your machine. 

I always hate that part because I never use the same OS or the same version of it. And so the packages, the way to install and configure it, are never the same. 

# Process

## 1: Update your machine

```bash
$ sudo apt update && sudo apt upgrade
```

## 2: Install Apache2

```bash
$ sudo apt install apache2 apache2-utils
```

## 3: Install PHP

```bash
$ sudo apt install php php-pgsql libapache2-mod-php
```

## 4: Install PostgreSQL

```bash
$ sudo apt install -y  postgresql libpq5 postgresql-9.5 postgresql-client-9.5 postgresql-client-common postgresql-contrib
```

## 5:(Optional) PhpPGAdmin

This is a User Interface based on providing an Admin Dashboard area

```bash
$ sudo apt install phppgadmin
```

## 6:Configuring Apache Server

You need to configure Apache virtual host configuration for phpPgAdmin.

Goto the '/etc/apache2/conf-available' directory and edit the configuration file 'phppgadmin.conf' with nano by typing:

```bash
$ sudo nano /etc/apache2/conf-available/phppgadmin.conf
```

Comment out the line '#Require local' by adding a # in front of the line and add below the line allow from all so that you can access from your browser.

```conf
Require all granted
```

Save and exit.

![photo1](https://www.howtoforge.com/images/how_to_install_postgresql_and_phppgadmin_on_ubuntu_1804/2.png)

## 7: Configure PHPPgAdmin

Go to the '/etc/phppgadmin' directory and edit the configuration file 'config.inc.php' by typing :

```bash
$ cd /etc/phppgadmin/config.inc.php
```

Find the line '$conf['extra_login_security'] = true;' and change the value to 'false' so you can login to phpPgAdmin with user postgres.

```php
$conf['extra_login_security'] = false;
```

Save and Exit.

!][photo2](https://www.howtoforge.com/images/how_to_install_postgresql_and_phppgadmin_on_ubuntu_1804/3.png)

Now restart the PostgreSQL and Apache2 services.

```bash
$ systemctl restart posqtgresql
$ systemctl restart apache2
```

## 8: Testing Postgres

By default, PostgreSQL is running on port '5432', and the Apache2 running on the default HTTP port '80'.

Check using netstat command.

```bash
$ sudo netstat -plntu
```

![photo3](https://www.howtoforge.com/images/how_to_install_postgresql_and_phppgadmin_on_ubuntu_1804/4.png)


Now access phpPgAdmin with your browser http://yourip/phppgadmin/.

![photo4](https://www.howtoforge.com/images/how_to_install_postgresql_and_phppgadmin_on_ubuntu_1804/5.png)

and then try login to with user 'postgres' and your password.

![photo5](https://www.howtoforge.com/images/how_to_install_postgresql_and_phppgadmin_on_ubuntu_1804/6.png)

After logging in, you will get this phpPgAdmin dashboard interface:

![photo6](https://www.howtoforge.com/images/how_to_install_postgresql_and_phppgadmin_on_ubuntu_1804/7.png)

The installation of PostgreSQL database with phpPgAdmin on ubuntu 18.04 has been completed successfully.


# Resources

+ [Medium Content](https://medium.com/@Riverside/how-to-install-apache-php-postgresql-lapp-on-ubuntu-16-04-adb00042c45d)
+ [How to forge](https://www.howtoforge.com/tutorial/ubuntu-postgresql-installation/)

# Conclusion

PostgreSQL is an advanced object-relational database management system (ORDBMS). It is Open Source and has a large and active Community. PostgreSQL provides the psql command line program as primary front-end, which can be used to enter SQL queries directly or execute them from a file. phpPgAdmin is a web-based administration tool for PostgreSQL written in PHP that makes the administration of Postgres databases easier.

![apache1](http://farm6.static.flickr.com/5064/5663284173_ded61414f2_o.jpg)