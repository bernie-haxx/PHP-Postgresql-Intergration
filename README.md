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