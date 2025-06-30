# freeCodeCamp article

src = https://www.freecodecamp.org/news/what-is-an-orm-the-meaning-of-object-relational-mapping-database-tools/

## Introduction

Object Relational Mapping is a technique used to create a bridge between object-oriented programs and relational databases. 
In other words, we can see the ORM as the layer that connects OOP (object-oriented programming) to relational databases.  

When interacting with a database using OOP languages, we have to perform different operations like creating, reading, updating,  
and deleting (CRUD) data. By design, we use SQL for performing these operations in relational databases.  

While using SQL for this purpose isn't necessarily a bad idea, the ORM and ORM tools help simplify the interaction between  
relational databases and different OOP languages.  

## What is an ORM tool?

It's software designed to help OOP developers interact with relational databases.  
So, instead of creating your own ORM software from scratch, you can make use of such tools.  

Here's an example of SQL code that retrieves information about a particular user from a database:
```sql
"SELECT id, name, email, phone_number FROM users WHERE id = 20"
```
The code above returns information about a user from a table called "users".  
Using the WHERE clause, we specified that the information should be from a user with an id of 20.  

On the other hand, an ORM tool can do the same query as above with simpler methods. That is:
```ts
users.getById(20)
```
ORM tools can generate methods like this one.  
Note that every ORM tool is built differently, so the methods are never the same, but the general purpose is similar.  

Most OOP languages have a variety of ORM tools that you can choose from.  

## Advantages of using ORM tools

- speeds up development time 
- decreases the cost of development
- handles the logic required to interact with databases
- improves security: ORM tools are built to eliminate the possibility of SQL injection attacks
- you write less code when using ORM tools than with SQL

## Disadvantages of using ORM tools

- learning how to use ORM tools can be time consuming
- they are likely not going to perform better when very complex queries are involved
- ORMs are generally slower than using SQL

---

# Alt.Bzh project

started with Baptiste on June 30  

Notre ORM doit gérér:
- la connexion à la BDD
- la prévention d'injections SQL
- la validation des données (gestion erreurs en amont)
- les erreurs en aval
- les requêtes (ajout/modif des lignes)
- les relations entre tables
- la création / modification des tables via le code = "migration"

## Structure d'un serveur SQL

Serveur > BDD > Table > Colonnes et Lignes

## SQL injection 

src = www.youtube.com/watch?v=8XVHftQskxk

### Definition

SQL injection is a form of cyberattack that exploits vulnerabilities in **web applications**.  
Atackers are able to manipulate a **database** by injecting **malicious SQL queries** through **user inputs**.   

### How does a SQL injection attack work?

Queries are used to retrieve or modify data from a database.  
Attackers exploit vulnerable input fields by injecting malicious SQL code that alters the intended behavior of the query.  

- Hackers first study the targeted database to understand its structure and behavior.
- Then they craft a SQL query that the server interprets as a legitimate command

### Basic Example

Consider a website that has a search feature where users can look for products by entering keywords.  
This website uses a SQL database to store product information.  

In a secure scenario, the website would take the user's input, sanitize it, and construct a SQL query to fetch the relevant products.  
For example: `SELECT * FROM products WHERE name LIKE '%entered_keyword%';`  

Let's say an attacker wants to retrieve all products from the database.  
In the search field, they enter ` OR '1'='1'; --`  

The query becomes: `SELECT * FROM products WHERE name LIKE '%' OR '1'='1'; --%';`  
- in this case, the attacker uses a single quote to close the existing string
- followed by ` OR '1'='1'` to inject a new condition that is always true
- the semicolon is used to terminate the statement
- the double hyphen is used to comment out the remaining portion of the original query

As a result, this query will retrieve all products from the database.  

Of course, this example is simplified for educational purposes. In the real world, SQL injections are much more sophisticated.  

### Types of SQL injection attacks

- In-band SQLi: includes error-based and union-based attacks where attackers use the same channel to launch an attack and collect the results
- inferential SQLi or Blind SQLi: involves sending data payloads to the DB server tp observe its response without directly seeing the results
  - it can be either boolean-based or time-based
- out-of-band SQLi: in cases where in-band SQLi is not possible, attackers leverage other channels, such as DNS or HTTP requests, to retrieve data from the DB

### Detecting and preventing SQL injections

- implement **input validation** and **parameterized queries**: validate and filter user input using an allowlist approach, and use parameterized queries to separate SQL code from user input.
- perform **regular security scans** to identify and address potential vulnerabilities in your web app
- keep all software up to date
