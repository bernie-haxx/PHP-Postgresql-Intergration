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
$ sudo apt install postgresql libpq5 postgresql-9.5 postgresql-client-9.5 postgresql-client-common postgresql-contrib
```

## 5:(Optional PhpPGAdmin)

This is a User Interface based on providing an Admin Dashboard area

```bash
sudo apt install phppgadmin
```
