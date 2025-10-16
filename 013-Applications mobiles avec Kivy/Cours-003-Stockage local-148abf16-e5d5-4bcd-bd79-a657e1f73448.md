# Formation : Applications mobiles avec Kivy

## Cours 003 : Stockage Local

### Introduction au stockage local

Le stockage local dans le développement d'applications mobiles est essentiel pour sauvegarder les données de l'application. Kivy, bien que principalement utilisé pour l'interface utilisateur, permet également de gérer le stockage de données localement. Ce cours vous fera découvrir les différentes options pour stocker des données localement dans une application Kivy.

### Objectifs de la formation
- Comprendre les besoins en stockage des applications mobiles.
- Découvrir les différentes méthodes de stockage en local disponibles dans Kivy.
- Apprendre à implémenter ces méthodes dans une application.

---

## Partie 1 : Besoins en stockage dans les applications mobiles

### 1.1 Pourquoi stocker des données localement ?
- **Performance** : Accès rapide aux données sans nécessiter une connexion internet.
- **Disponibilité** : Les données sont accessibles même hors ligne.
- **Expérience utilisateur** : Permet d’offrir une expérience fluide en enregistrant les préférences de l’utilisateur ou l’état de l'application.

### 1.2 Types de données à stocker
- Données utilisateur (préférences, réglages)
- Historique d'utilisation
- Données d'application (cache, états)

---

## Partie 2 : Méthodes de stockage en local dans Kivy

### 2.1 Utilisation de fichiers
- **Stockage simple** : Ecrire et lire des données dans des fichiers texte.
- **Exemple d'écriture dans un fichier** :
  ```python
  with open('data.txt', 'w') as f:
      f.write('Ceci est un exemple de stockage local.\n')
  ```
- **Exemple de lecture d'un fichier** :
  ```python
  with open('data.txt', 'r') as f:
      contenu = f.read()
      print(contenu)
  ```

### 2.2 Utilisation de SQLite
- Kivy supporte SQLite, une base de données légère.
- **Installation** : Assurez-vous d'avoir SQLite installé.
- **Créer une base de données** :
  ```python
  import sqlite3
  connexion = sqlite3.connect('database.db')
  curseur = connexion.cursor()
  curseur.execute('CREATE TABLE IF NOT EXISTS utilisateurs(id INTEGER PRIMARY KEY, nom TEXT)')
  connexion.commit()
  ```
- **Insertion de données** :
  ```python
  curseur.execute('INSERT INTO utilisateurs(nom) VALUES(?)', ('Jean',))
  connexion.commit()
  ```
- **Lecture de données** :
  ```python
  curseur.execute('SELECT * FROM utilisateurs')
  resultats = curseur.fetchall()
  print(resultats)
  ```

### 2.3 Utilisation du JSON
- **Stockage de données en format JSON** : Pratique pour sauvegarder des données basées sur des objets.
- **Écriture de données dans un fichier JSON** :
  ```python
  import json
  data = {'nom': 'Jean', 'age': 30}
  with open('data.json', 'w') as f:
      json.dump(data, f)
  ```
- **Lecture de données depuis un fichier JSON** :
  ```python
  with open('data.json', 'r') as f:
      data_read = json.load(f)
      print(data_read)
  ```

---

## Partie 3 : Pratiques recommandées

### 3.1 Protection des données
- Utiliser des techniques telles que le chiffrement pour protéger les informations sensibles.
- Ne pas stocker d'informations critiques sans une méthode de protection.

### 3.2 Gestion des erreurs
- Toujours gérer les exceptions lors de la lecture/écriture des fichiers ou bases de données.

---

## Conclusion

Le stockage local est une compétence indispensable pour tout développeur d'applications mobiles utilisant Kivy. Grâce aux différentes méthodes de stockage, vous pouvez créer des applications plus réactives et user-friendly. Pratiquez ces concepts en les intégrant dans vos projets Kivy pour approfondir vos compétences en développement mobile.

### Ressources complémentaires
- Documentation de Kivy : https://kivy.org/doc/stable/
- Tutoriels SQLite : https://www.sqlitetutorial.net/
- Documentation JSON : https://www.json.org/json-en.html
