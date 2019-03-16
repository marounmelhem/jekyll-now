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
- MongoDB vs mySQL (head to head comparison)
- Live MongoDB vs mySQL performance, scalability, ease of use test using Laravel framework with VueJS



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

__NB: MongoDB is available for Linux, MacOS and Windows__

![13.png](http://c1.maroun.xyz/github_screenshots/13.png)




