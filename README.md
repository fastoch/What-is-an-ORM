# freeCodeCamp article

src = https://www.freecodecamp.org/news/what-is-an-orm-the-meaning-of-object-relational-mapping-database-tools/

## Introduction

Object Relational Mapping is a technique used to create a bridge between object-oriented programs and, in most cases, relational databases. 
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

### Définition

### Comment s'en prémunir ?



