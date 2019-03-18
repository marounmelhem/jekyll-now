---
published: true
---
_As per the official MongoDB documentation_

> _ MongoDB is a document database with the scalability and flexibility that you want with the querying and indexing that you need_


**How does MongoDB work?**

> MongoDB stores data in flexible, JSON-like documents, meaning fields can vary from document to document and data structure can be changed over time__


**What are the alternatives?**

When choosing a database for your project, one of the biggest and most important decision is picking a relational (SQL) or non-relational (noSQL) data structure.

While both options can get the job done, there are mentionable key differences that each developer must keep in mind.



**What we'll be talking about?**

- What are the benefits of using MongoDB
- How to setup MongoDB on Ubuntu 16.04 (using php)
- MongoDB tools you should use
- Let's talk about mySQL
- MongoDB vs MySQL
- MongoDB/MySQL Coding example



**Is the test live?**

YES! the test along with all used code can be checked through [c1.maroun.xyz](c1.maroun.xyz)



## What are the benefits of using MongoDB

**MongoDB's schema less nature**

MongoDB is a document database in which one collection holds different documents. Number of fields, content and size of the document can differ from one document to another.


**Ease of scale-out**

Unlike RDBMS databases, MongoDB is easy to scale since it requires a lot less resources.


**Structure of a single object is clear.**

**No complex joins.**


**Deep query-ability. MongoDB supports dynamic queries on documents using a document-based query language that's nearly as powerful as SQL.**


**Uses internal memory for storing the (windowed) working set, enabling faster access of data.**



## How to setup MongoDB on Ubuntu 16.04 (using php)

**Login via ssh**

![1.png](http://c1.maroun.xyz/github_screenshots/1.png)


**Create site folder and configure permissions**

![3.png](http://c1.maroun.xyz/github_screenshots/3.png)


**Create site conf in /etc/apache2/sites-available**

![5.png](http://c1.maroun.xyz/github_screenshots/5.png)


**Enable site in /etc/apache2/sites-available**

![7.png](http://c1.maroun.xyz/github_screenshots/7.png)


**Updating packages**

```
sudo apt update
```

**INSTALL MONGODB**

```
sudo apt install -y mongodb
```

**Verifying the service and database**

```
sudo systemctl status mongodb
```

**Starting MongoDB**

```
sudo systemctl start mongodb
```

**Restarting MongoDB**

```
sudo systemctl restart mongodb
```

**Stopping MongoDB**

```
sudo systemctl stop mongodb
```

**Installing MongoDB php extension**

```
sudo apt-get install php-mongodb
```

**Installing MongoDB if php is already installed**
```
sudo apt install php7.2-mongodb
sudo pecl install mongodb
sudo bash
sudo echo "extension=mongodb.so" >> /etc/php/7.2/apache2/php.ini
```

**Installing MongoDB if php is not installed**
```
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:ondrej/php
sudo apt update
sudo apt install php7.2 libapache2-mod-php7.2 php7.2-common php-7.2-cli php7.2-mongodb php-pear php7.2-dev
```

![10.png](http://c1.maroun.xyz/github_screenshots/10.png)

**Restart apache2**
```
sudo apachectl restart
```

**Verify MongoDB installation by adding phpinfo file**
```
sudo vim /var/www/html/info.php
```

**Add phpinfo function**
```
<?php
phpinfo();
?>
```

**Save created file ":x!" command**
![11.png](http://c1.maroun.xyz/github_screenshots/11.png)


**Verify MongoDB installation from phpinfo (website.com/info.php)**
![12.png](http://c1.maroun.xyz/github_screenshots/12.png)


**INSTALL MONGODB (For Mac OSX users)**

If you don't have brew installed, you should:
https://brew.sh/

```
brew update
brew install mongodb
```

## MongoDB tools you should use

If you usually use MySQL you're probably know tools like __phpmyadmin__. It's the easiest way to manage MySQL data on the server.

Well, for MongoDB, there's a tool called RoboMongo and here's how you install it:

```
wget https://download.robomongo.org/0.8.5/linux/robomongo-0.8.5-x86_64.deb
```
```
sudo dpkg -i robomongo-0.8.5-x86_64.deb
```
```
robomongo
```

__NB:__
__-MongoDB is available for Linux, MacOS and Windows__
__-Another option that can be used is MongoDB Compass__

![13.png](http://c1.maroun.xyz/github_screenshots/13.png)


**Compass on Mac OSX example**
![18.png](http://c1.maroun.xyz/github_screenshots/18.png)


## Let's talk about MySQL

**A note about SQL**

SQL on the other hand stands for structured query language.

SQL is the standardized language used to access the database.

SQL contains three parts:

- Data definition language includes statements that help you define the database and its objects, e.g., tables, views, triggers, stored procedures, etc.
- Data manipulation language contains statements that allow you to update and query data.
- Data control language allows you to grant the permissions to a user to access specific data in the database.

**What about MySQL?**

MySQL is a full-featured open-source relational database management system (RDBMS) that was originally built by MySQL AB and currently owned by Oracle Corporation. It stores data in tables that are grouped into a database, uses Structured Query Language (SQL) to access data and such commands as ‘SELECT’, ‘UPDATE’, ‘INSERT’ and ‘DELETE’ to manage it. Related information can be stored in different tables, but the usage of JOIN operation allows you to correlate it, perform queries across various tables and minimize the chance of data duplication.

MySQL is compatible with nearly all operating systems, namely Windows, Linux, Unix, Apple, FreeBSD and many others. It supports various storage engines, like InnoDB (it is the default one), Federated, MyISAM, Memory, CSV, Archive, Blackhole and Merge.


## MongoDB vs MySQL (head to head comparison)

**A note about relational/non relational databases:**

The relational databases held the leadership for decades and at that time the choice was quite obvious, either MySQL, Oracle, or MS SQL, just to name a few. They’ve served as a basis for tons of enterprise applications, while modern apps require more diversity and scalability. Non-relational databases, like MongoDB, have appeared to meet the existing requirements and replace current relational environment.


**Side by side comparison:**

![14.png](http://c1.maroun.xyz/github_screenshots/14.png)


**MySQL vs MongoDB: pros and cons**

Comparing MongoDB vs MySQL performance is difficult, since both management systems are extremely useful and the core differences underlie their basic operations and initial approach. However, MongoDB vs MySQL is a hot argument that is going on for a while now: mature relational database against a young non-relational system. Both are open-source and easily available, as well as both systems offer commercial versions with tons of additional features.

![15.png](http://c1.maroun.xyz/github_screenshots/15.png)


**Which database to choose?**

To answer the main question: “when to use MongoDB instead of MySQL?” you need to take into account your project requirements and further goals. MySQL is well-recognized for its high performance, flexibility, reliable data protection, high availability, and management ease. Proper data indexing can solve the issue with performance, facilitate interaction and ensure robustness. But if your data is unstructured and complex, or if you can’t pre-define your schema, you’d better opt for MongoDB. And what is more, if you need to handle a large volume of data and store it as documents — MongoDB will help you to meet the challenges.


## MongoDB/MySQL Coding example

Let's start coding!

**Setting up a sample database**

In order to code our own testing environment (for both mongoDB and mysql), we need a sample database. We're gonna use MySQL's default one:

https://github.com/datacharmer/test_db


**Setting up on MySQL and importing test DB**

```
 mysql -u root -p < ~/Desktop/test_db-master/employees.sql
```

![16.png](http://c1.maroun.xyz/github_screenshots/16.png)


**Verify MySQL database import**

![17.png](http://c1.maroun.xyz/github_screenshots/17.png)


**Setting up on MongoDB and importing test DB**

For MongoDB it's actually easier to import the test DB, you can find one through:

```
http://media.mongodb.org/zips.json
```

Download it and add it to your desktop (or to any location you desire).

```
cd ~/Desktop
mongoimport -v --file=zips.json
```

![18.png](http://c1.maroun.xyz/github_screenshots/18.png)
