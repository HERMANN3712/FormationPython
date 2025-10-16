# Formation Python: Fichiers et Exceptions - Modules os et csv

## Introduction
Dans cette formation, nous allons explorer les modules `os` et `csv` en Python, essentiels pour gérer les fichiers et les données dans des formats tabulaires. Nous aborderons les concepts de base, les bonnes pratiques et des exemples concrets.

---

## Plan de la formation
1. **Introduction aux fichiers en Python**  
   1.1. Qu'est-ce qu'un fichier ?  
   1.2. Types de fichiers  
   1.3. Ouverture et fermeture de fichiers

2. **Module os**  
   2.1. Introduction au module os  
   2.2. Fonctions de base  
       - `os.getcwd()` : Récupérer le répertoire de travail courant  
       - `os.listdir(path)` : Lister les fichiers et dossiers  
       - `os.mkdir(path)` : Créer un nouveau dossier  
       - `os.rename(src, dst)` : Renommer un fichier ou un dossier
   2.3. Gestion des chemins  
       - `os.path.join()` : Construire des chemins  
       - `os.path.exists(path)` : Vérifier l'existence d'un fichier/dossier
   2.4. Exemples pratiques

3. **Module csv**  
   3.1. Introduction au module csv  
   3.2. Lecture de fichiers CSV  
       - `csv.reader()` : Lire des fichiers CSV  
   3.3. Écriture de fichiers CSV  
       - `csv.writer()` : Écrire des fichiers CSV  
   3.4. Gestion des fichiers CSV avec `DictReader` et `DictWriter`
   3.5. Exemples pratiques

4. **Gestion des exceptions**  
   4.1. Introduction aux exceptions  
   4.2. Types d'exceptions courantes  
   4.3. Utilisation de `try`, `except`, `finally`  
   4.4. Lever des exceptions

5. **Conclusion**  
   5.1. Résumé des points clés  
   5.2. Questions et réponses

---

## Détails de la formation

### 1. Introduction aux fichiers en Python
#### 1.1 Qu'est-ce qu'un fichier ?
Un fichier est un ensemble de données stockées sur un support de stockage. En Python, vous pouvez interagir avec ces fichiers par le biais de divers moyens.

#### 1.2 Types de fichiers
- **Textuels** : Fichiers contenant des données lisibles par l'homme (ex : `.txt`, `.csv`)
- **Binaires** : Fichiers contenant des données non lisibles par l'homme (ex : `.png`, `.exe`)

#### 1.3 Ouverture et fermeture de fichiers
En Python, vous pouvez ouvrir un fichier en utilisant la fonction `open()`, et le fermer avec `close()`. Voici un exemple :
```python
file = open('exemple.txt', 'r')  # Ouvrir le fichier en mode lecture
# ...
file.close()  # Fermer le fichier
```

### 2. Module os
#### 2.1 Introduction au module os
Le module `os` vous permet d'interagir avec le système d'exploitation et de gérer les fichiers et les répertoires.

#### 2.2 Fonctions de base
- **`os.getcwd()`** : Récupérer le répertoire de travail courant.
- **`os.listdir(path)`** : Lister les fichiers et dossiers dans un répertoire spécifié.
- **`os.mkdir(path)`** : Créer un nouveau dossier.
- **`os.rename(src, dst)`** : Renommer un fichier ou un dossier.

#### 2.3 Gestion des chemins
- Utilisez `os.path.join()` pour construire des chemins de manière sûre.
- Vérifiez si un chemin existe avec `os.path.exists(path)`.

#### 2.4 Exemples pratiques
```python
import os
# Liste des fichiers dans le répertoire courant
fichiers = os.listdir(os.getcwd())
print(fichiers)
```

### 3. Module csv
#### 3.1 Introduction au module csv
Le module `csv` simplifie la lecture et l'écriture des fichiers CSV (Comma-Separated Values).

#### 3.2 Lecture de fichiers CSV
Utilisez `csv.reader()` pour lire des fichiers CSV :
```python
import csv
with open('fichier.csv', mode='r') as fichier:
    lecteur = csv.reader(fichier)
    for ligne in lecteur:
        print(ligne)
```

#### 3.3 Écriture de fichiers CSV
Utilisez `csv.writer()` pour écrire dans un fichier CSV :
```python
with open('fichier.csv', mode='w', newline='') as fichier:
    ecrivain = csv.writer(fichier)
    ecrivain.writerow(['Nom', 'Âge'])
    ecrivain.writerow(['Alice', 30])
```

#### 3.4 Gestion des fichiers CSV avec `DictReader` et `DictWriter`
Utilisez `csv.DictReader()` et `csv.DictWriter()` pour travailler avec des dictionnaires :
```python
with open('fichier.csv', mode='r') as fichier:
    lecteur = csv.DictReader(fichier)
    for ligne in lecteur:
        print(ligne['Nom'], ligne['Âge'])
```

### 4. Gestion des exceptions
#### 4.1 Introduction aux exceptions
Les exceptions sont des événements qui se produisent lors de l'exécution de votre programme, entraînant un comportement inattendu.

#### 4.2 Types d'exceptions courantes
- `FileNotFoundError`
- `IOError`
- `ValueError`

#### 4.3 Utilisation de `try`, `except`, `finally`
```python
try:
    # code qui peut produire une exception
except ValueError:
    # code à exécuter si une ValueError se produit
finally:
    # code à exécuter quoiqu'il arrive
```

### 5. Conclusion
#### 5.1 Résumé des points clés
- Importance des modules `os` et `csv` pour manipuler les fichiers.
- Techniques de gestion des exceptions pour rendre le code plus robuste.

#### 5.2 Questions et réponses
N'hésitez pas à poser vos questions pour clarifier des points discutés.