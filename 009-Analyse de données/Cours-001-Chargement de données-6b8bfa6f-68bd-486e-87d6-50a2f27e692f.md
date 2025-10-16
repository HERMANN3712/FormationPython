# Formation sur l'Analyse de données : Chargement de données

## Objectifs de la formation
- Comprendre les différentes sources de données et formats.
- Apprendre à charger des données à partir de fichiers CSV, Excel et bases de données.
- Utiliser des bibliothèques Python pour le chargement de données.

## Plan de la formation

### 1. Introduction à l'Analyse de données
- Qu'est-ce que l'analyse de données ?
- Importance du chargement de données dans le processus d'analyse.

### 2. Sources de données
- Types de sources : fichiers, API, bases de données.
- Formats courants : CSV, JSON, Excel, SQL.

### 3. Chargement de données à partir de fichiers CSV
- Utilisation de la bibliothèque `pandas`.
- Lecture de fichiers CSV avec `pd.read_csv()`.
- Exemple de chargement d'un fichier CSV.

  ```python
  import pandas as pd
  df = pd.read_csv('chemin/vers/fichier.csv')
  print(df.head())
  ```

### 4. Chargement de données à partir de fichiers Excel
- Lecture de fichiers Excel avec `pd.read_excel()`.
- Gestion des feuilles et des index.

  ```python
  df = pd.read_excel('chemin/vers/fichier.xlsx', sheet_name='Feuille1')
  print(df.head())
  ```

### 5. Chargement de données à partir de bases de données
- Utilisation de `SQLAlchemy` pour se connecter à une base de données.
- Chargement de données avec `pd.read_sql()`.

  ```python
  from sqlalchemy import create_engine
  engine = create_engine('sqlite:///chemin/vers/database.db')
  df = pd.read_sql('SELECT * FROM table', engine)
  print(df.head())
  ```

### 6. Chargement de données depuis d'autres sources
- API web : Utilisation de `requests` pour charger des données JSON.
- Exemple de chargement de données depuis une API.

  ```python
  import requests
  response = requests.get('https://api.exemple.com/donnees')
  data = response.json()
  ```

### 7. Traitement des erreurs lors du chargement
- Gestion des exceptions avec `try` et `except`.
- Comment résoudre les problèmes courants lors du chargement des données.

### 8. Conclusion et ressources supplémentaires
- Récapitulatif des points clés.
- Ressources pour aller plus loin : documentation de `pandas`, `SQLAlchemy`, etc.

---

## Exercices pratiques
- Exercice 1 : Charger un fichier CSV et afficher les 10 premières lignes.
- Exercice 2 : Charger un fichier Excel et afficher toutes les feuilles.
- Exercice 3 : Connectez-vous à une base de données et exécutez une requête SQL.

## Informations supplémentaires
- Durée : 2 heures
- Pré-requis : Avoir installé Python et les bibliothèques nécessaires (`pandas`, `SQLAlchemy`, `requests`).

---

Merci pour votre attention ! 

Pour toute question, n'hésitez pas à me contacter.