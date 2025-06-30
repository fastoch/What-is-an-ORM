src = https://www.freecodecamp.org/news/what-is-an-orm-the-meaning-of-object-relational-mapping-database-tools/

# Definition

Object Relational Mapping is a technique used to create a bridge between object-oriented programs and, in most cases, relational databases. 
In other words, we can see the ORM as the layer that connects OOP (object-oriented programming) to relational databases.  

# Alt.Bzh project

Notre ORM doit gérér:
- la connexion à la BDD
- la prévention d'injections SQL
- la validation des données (gestion erreurs en amont)
- les erreurs en aval
- les requêtes (ajout/modif des lignes)
- les relations entre tables
- la création / modification des tables via le code = "migration"

# Structure d'un serveur SQL

Serveur > BDD > Table > Colonnes et Lignes

