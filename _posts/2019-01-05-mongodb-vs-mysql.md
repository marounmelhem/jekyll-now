---
published: false
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
![1.png]({{site.baseurl}}/_posts/1.png)


**Create site folder and configure permissions**
![3.png]({{site.baseurl}}/_posts/3.png)


**Create site conf in /etc/apache2/sites-available**
![5.png]({{site.baseurl}}/_posts/5.png)


**Enable site in /etc/apache2/sites-available**
![7.png]({{site.baseurl}}/_posts/7.png)


**Add MongoDB Repository**

```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5
```

```
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.6 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.6.list
```

![8.png]({{site.baseurl}}/_posts/8.png)


**INSTALL MONGODB**

```
sudo apt update
sudo apt install mongodb-org mongodb-org-server
```

if you face the "E: Unable to locate package mongodb-org  //This is the error" error, check:
https://stackoverflow.com/a/28966356/3766571

![9.png]({{site.baseurl}}/_posts/9.png)


