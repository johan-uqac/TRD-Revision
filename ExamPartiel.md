# Examen partiel base de données

## Introduction

### C'est quoi une donnée ?

Une donnée est un fait, un chiffre, un texte, une image, une vidéo, collectée dans le but d'être analysée, examinée et utilisée pour aider à la prise de décision

#### Exemple de donnée

- Texte
- Image
- Vidéo
- Nombre
- Enregistrement audio
- Liste de clients
- ...

#### Rôle de la donnée

Fondement de l'information et de la connaissance. Essentiel dans de multiples domaines comme l'éducatio, la science, la finance, la technologie, ...

### Type de données

**Données structurées** :

- Organisées dans un format défini donc simple à rechercher/manipuler. **Base de données _relationnelle_**

**Données non structurées** :

- Non organisées, format varié, plus difficile à traiter et à analyser. **Base de données _non-relationnelle_**

**Distinction** :

- Fait varier le stockage, le traitement, l'analyse et la système de gestion de base de données (SGBD)

### Importance des données

- Prise de décision basé sur les données;
- Personnalisation et ciblage : Utilisation des données pour offrir des expériences personnalisées aux clients;
- Innovation et développement;

### Utilisation des données

- Secteur commercial : Comportement des consommateurs
- Santé : Recherche médicale, dossier des patients, gestion des traitements
- Education : Suivi des performances des étudiants, personnalisation de l'apprentissage
- Gouvernement : Planification urbaine, sécurité nationale
- ...

### Définition de base de données

- Ensemble organisé de données stockées et accessibles électroniquement
- Ensemble structuré de données apparentées qui modélisent un univers réel
- Ensemble structuré de données cohérentes et pérennes

### Importance des bases de données

- Représente les données du monde réel
- Enregistre les données
- Manipuler les données et en tirer des informations pour prendre des décisions
- Contrôler les données
- Partager les données
- Sécuriser les données

### Types de base de données

#### Base de données relationnelles

- Organisation des données en tables et en colonnes
- Language standardisé pour manipuler les données
- Modèle dominant

#### Base de données non-relationnelles

- noSQL : Not Only SQL
- Objet : stockage persistant des objets
- XML : documents semi-structurés
- Spatial : données géographiques
- Hiérarchique/réseau : Anciens modèles

### Système de gestion de base de données (SGBD)

- DBMS : Database Management System

- Logiciel qui permet de créer, interroger, mettre à jour et administrer une base de données
- Seule interface entre les données et les informaticiens

#### Composants clés d'un SGBD

- Serveur de données ou serveur de base de données pour le stockage et la gestion des données
- Moteur de traitement des requêtes pour l'interprétation et l'éxecution des requêtes
- Interface utilisateur pour intéragir avec la base de données
- Outils d'administration pour maintenance, configuration, optimisation du SGBD
- Mécanisme de sécurité et réplication des données

### Choix d'un SGBD

- Performance
- Coût
- Sécurité
- Scalabilité
- Facilité d'utilisation

## Conception de BDD relationnelle

### Prédecessurs

- Modèle hiérarchique : Entités reliées par des associations de type parent/enfant (arborescence)
- Modèle en réseau : Entités reliées par des associations de type propriétaire/membre comme des pointeurs (graphes)

### Histoire

- 1970 : Edgar Codd, IBM, propose le modèle relationnel
- Modèle standard pour les bases de données et dominant
- Succès dû à sa simplicité, sa flexibilité et sa puissance
- Fondé sur la théorie des ensembles et la notion de relation

### Théorie des ensembles

- Ensemble : Collection d'objets
- Relation : Ensemble de ligne (tuples) ayant les mêmes attributs (colonnes)

- Branche des mathématiques qui étudie les ensembles et les liens entre eux

- Une relation est une table où chaque ligne représente un enregistrement et chaque colonne représente un champ de données

### Nommée après

- Organisation des données en tables relationnelles
- Exploitation des principes mathématiques de la théorie des ensembles (union, intersection, différence, produit cartésien, ...)
- Capacité à maintenir les liens entre les tables pour assurer l'intégrité et la cohérence des données

### Conception

Merise, pas UML

#### Etapes

- Collecte des besoins (interview / analyses de données existantes), se concrétise par la mise en place d'un dictionnaire de données
- Modèle Conceptuel des Données (MCD) : Représentation graphique de l'ensemble des données recensées
- Modèle Logique des Données (MLD) : Représentation graphique de l’ensemble des données tel qu’il sera implémenté dans une base de données
- Modèle Physique des Données (MPD) : Implémentation de l’ensemble des données dans une base de données

##### Collecte des besoins

- Identifier les besoins : recueillir les exigences du système d'information
- Analyser les besoins : comment les besoins influent sur la conception de la base de données
- Modéliser les besoins : représenter les besoins sous forme d'un dictionnaire de données
- Valider et réviser : valider les besoins avec les utilisateurs et les réviser si nécessaire

**Dépendance fonctionnelle** :

- Aide à la compréhension des données et les relations entre elles
- Permet de déterminer les clés primaires et les clés étrangères
- Permet de déterminer les entités qui feront partie du modèle conceptuel des données

##### Modèle Conceptuel des Données (MCD)

**Définition** :

- Représentation graphique simple des données utilisées par le système d’information
- Permet de visualiser les données et les relations entre elles
- Vision claire et logique de la structure des données
- Compréhensible par tout le monde
- Schéma Entité-Association

**Etapes** :

- Entité : Regroupement de données se rapportant à un même ensemble

- Regroupement des données par entité (Toute donnée de l'entité est appelée propriété qui a un type, chaque entité a une clié primaire (identifiant unique))
- Recherche d'associations (lien entre les entités), on utilise un verbe pour décrire l'association
- Détermination des cardinalités (nombre d'occurences d'une entité par rapport à une autre) :
  - 0-n : Zéro à plusieurs
  - 1-1 : Un à un
  - 1-n : Un à plusieurs
  - n-n : Plusieurs à plusieurs

**Cas particuliers** :

- Association porteuse : Association qui a des propriétés, ex: Inscription (date d'inscription)
- Association réflexive : Association d'une entité avec elle-même, ex: Employé supervise un autre employé

**Passage de MCD à MLD** :

Remplacer les entités et les associations par des relations

Une relation est composée de :

- Attributs : Données élémentaires issues des propriétés des différentes entités
- Nom : Nom de l'entité ou de l'association qui lui correspond
- Clé primaire : Identifiant de l'entité ou de l'association

_Règles de passage_ :

- Entité devient relation (table) :
  - Propriétés deviennent attributs (colonnes)
  - Identifiant devient clé primaire
- Association avec des cardinalités 0,n ou 1,n devient une relation associative
  - Clé primaire composée des identifiants des entités reliées
  - Identifiants seront donc également des clés étrangères respectives
- Association avec cardinalité 1,1 devient une relation simple
  - Ajouter la clé étrangère dans la relation qui a la cardinalité 1
  - Association non porteuse de données
  - Association binaire

## Création de BDD

- Donner un nom approprié à la base de données
- Schéma logique des données : Vue graphique de la manière dont les données sont organisées, les tables et les relations entre elles
- Dictionnaire de données : Détail de chaque table, y compris le nom des colonnes, leur type et leur taille

## Normalisation des données

### Définition

- Processus utilisé dans la conception de base de données pour organiser les données de manière à réduire la redondance et le risque d'anomalie de mise à jour
- Garantir que les données sont stockées de manière logique, cohérente et efficace
- Fondée sur l'ensemble de règles appelées formes normales, élaborées par Edgar Frank Codd en 1970

| Forme normale            | Description                                                                                                                   |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| 1ereFormeNormale         | Chaque colonne contient des valeurs atomiques, et pas de valeurs répétitives (pas Adresse par exemple car trop complexe)      |
| 2emeFormeNormale         | Tout attribut de la relation doit dépendre intégralement de toute la clé et non d’une partie de la clé                        |
| 3emeFormeNormale         | Les attributs n’appartenant pas à la clé ne dépendent pas d’un attribut non-clé                                               |
| FormeNormaledeBoyce-Codd | Les seules dépendances fonctionnelles élémentaires qu’elle comporte sont celles dans lesquelles une clé détermine un attribut |

## Langage SQL

### Histoire

- SQL : Structured Query Language
- Créé par IBM au début des années 1970
- Première version commerciale en 1979 par Oracle Corporation autrefois appelé Relational Software

### Présentation

- Langage de requête standard pour gérer et manipuler des bases de données relationnelles

Découpé en plusieurs sous-ensembles:

- LDD : Langage de Définition de Données, regroupe les commandes permettant de créer, modifier et supprimer des objets de la base de données (tables, colonnes, contraintes, relations, ...) CREATE, ALTER, DROP
- LMD : Langage de Manipulation de Données, regroupe les commandes permettant de manipuler les données (INSERT, UPDATE, DELETE, SELECT)
- LCD : Langage de Contrôle de Données, regroupe les commandes permettant de gérer les droits d'accès aux données (GRANT, REVOKE)

### LDD

#### Types de données

- Numérique :

  - TINYINT / SMALLINT / MEDIUMINT / BIGINT / DECIMAL / NUMERIC / FLOAT / DOUBLE / REAL
  - AUTO_INCREMENT : Incrément automatique
  - UNSIGNED : Valeurs positives
  - ZEROFILL : Remplissage avec des zéros, automatiquement activé avec UNSIGNED

- Caractère :

  - CHAR : Chaine de caractères de taille fixe
  - VARCHAR : Chaine de caractères de taille variable
  - NCHAR / NVARCHAR : Chaine de caractères spéciaux comme chinois / hébreux / russe, nombre d'octets doublé
  - TEXT / NTEXT : Amené à disparaitre
  - VARBINARY / BINARY / TINYBLOB / BLOB / MEDIUMBLOB / LONGBLOB : Stockage de données binaires

- Temporel :

  - DATE : Date au format 'YYYY-MM-DD' (1000-01-01 à 9999-12-31)
  - DATETIME : Date et heure au format 'YYYY-MM-DD HH:MM:SS' (1000-01-01 00:00:00 à 9999-12-31 23:59:59)
  - TIMESTAMP : Date et heure au format 'YYYY-MM-DD HH:MM:SS', stocké au format UNIX (1970-2037)
  - TIME : Heure au format 'HH:MM:SS' (-838:59:59 à 838:59:59)
  - YEAR : Année au format 'YYYY' (1901 à 2155)

- Autres :
  - Géographique
  - Spatiales
  - Spécifiques (JSON, XML, URL, SET, ENUM, BOOLEAN, ...)

## Commandes SQL

**INSERT** Insertion de données dans une table

```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

**SELECT** Sélection de données dans une table

```sql
SELECT column1, column2, ... FROM table_name;
OU
SELECT * FROM table_name;
```

_ORDER BY_ Tri des résultats

```sql
SELECT column1, column2, ... FROM table_name
ORDER BY column1 ASC|DESC;
```

_DISTINCT_ Sélection des valeurs uniques : Pas de doublons, par défaut _ALL_ (implicitement)

```sql
SELECT DISTINCT column1, column2, ... FROM table_name;
```

_LIMIT_ Limite le nombre de résultats

```sql
SELECT column1, column2, ... FROM table_name LIMIT 5;
```

_AS_ Alias pour les colonnes ou les tables

```sql
SELECT column1 AS 'Alias1', column2 AS 'Alias2', ... FROM table_name AS 'AliasTable';
```

### Conditions

_WHERE_ Filtre les résultats

```sql
SELECT age FROM clients WHERE age > 18;
```

Possible d'utiliser les opérateurs logiques _AND_, _OR_

**NE PAS UTILISER _=_ OU _!=_ POUR LES NULL MAIS _IS NULL_ OU _IS NOT NULL_**

```sql
SELECT * FROM clients WHERE nom IS NULL;
```

_BETWEEN_ Sélectionne des valeurs dans une plage

_IN_ Sélectionne des valeurs parmi une liste

_NOT IN_ Sélectionne des valeurs qui ne sont pas dans une liste

_LIKE_ Sélectionne des valeurs qui correspondent à un modèle :

- % : N'importe quelle chaine de caractères
- %a : N'importe quelle chaine de caractères qui se termine par 'a'
- a% : N'importe quelle chaine de caractères qui commence par 'a'
- %a% : N'importe quelle chaine de caractères qui contient 'a'
- co%ge : Commence par 'co' et se termine par 'ge'
- a_b : 'a' suivi d'un seul caractère suivi de 'b'

_CASE_ Sélectionne des valeurs en fonction d'une condition

```sql
SELECT nom, age, CASE WHEN age < 18 THEN 'Mineur' ELSE 'Majeur' END AS 'Statut' FROM clients;
```

### Opérateurs numériques

Effectue des opérations mathématiques sur les colonnes de type numérique

```sql
SELECT salaire * 1.2 AS nouveau_salaire FROM employes;
```
