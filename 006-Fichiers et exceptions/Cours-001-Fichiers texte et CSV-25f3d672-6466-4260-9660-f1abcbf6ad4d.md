# Formation : Fichiers et Exceptions en Python

## Introduction

Dans cette formation, nous aborderons le travail avec des fichiers texte et CSV en Python. Nous verrons comment ouvrir, lire, écrire, et manipuler ces fichiers, ainsi que comment gérer les exceptions qui peuvent survenir lors de ces opérations.

## Plan de la formation

1. **Introduction aux fichiers**  
   1.1. Qu'est-ce qu'un fichier ?  
   1.2. Types de fichiers en informatique  
   1.3. Introduction aux fichiers texte et CSV

2. **Lire des fichiers texte**  
   2.1. Ouvrir un fichier avec `open()`  
   2.2. Lire le contenu d'un fichier  
   2.3. Fermer un fichier

3. **Écrire dans des fichiers texte**  
   3.1. Ouvrir un fichier en mode écriture  
   3.2. Écrire du texte dans un fichier  
   3.3. Ajouter du texte à un fichier existant

4. **Travailler avec des fichiers CSV**  
   4.1. Qu'est-ce qu'un fichier CSV ?  
   4.2. Lire un fichier CSV avec `csv`  
   4.3. Écrire dans un fichier CSV

5. **Gestion des exceptions**  
   5.1. Pourquoi gérer les exceptions ?  
   5.2. Utiliser `try`, `except` et `finally`  
   5.3. Exceptions courantes lors du travail avec des fichiers

6. **Exercices pratiques**  
   6.1. Lire un fichier texte et afficher son contenu  
   6.2. Écrire des données dans un fichier texte  
   6.3. Créer et manipuler un fichier CSV  
   6.4. Gérer les exceptions dans les opérations sur les fichiers  

7. **Conclusion**  
   7.1. Récapitulatif des concepts abordés  
   7.2. Ressources supplémentaires

## 1. Introduction aux fichiers

### 1.1. Qu'est-ce qu'un fichier ?
Un fichier est une collection de données ou d'informations qui sont stockées sur un support de stockage (comme un disque dur, une clé USB, etc.).  

### 1.2. Types de fichiers en informatique
Les fichiers peuvent être classés en plusieurs catégories, notamment :  
- Fichiers texte  
- Fichiers binaires  

### 1.3. Introduction aux fichiers texte et CSV
Les fichiers texte contiennent des caractères codés, tandis que les fichiers CSV (Comma-Separated Values) sont souvent utilisés pour stocker des données tabulaires sous forme de texte.  

## 2. Lire des fichiers texte

### 2.1. Ouvrir un fichier avec `open()`
Pour lire un fichier en Python, on utilise la fonction `open()`. Voici comment l'utiliser :  
```python
fichier = open('chemin/vers/fichier.txt', 'r')  # 'r' pour lecture
```

### 2.2. Lire le contenu d'un fichier
On peut lire le contenu du fichier en utilisant plusieurs méthodes :  
- `fichier.read()` : lit tout le contenu du fichier  
- `fichier.readline()` : lit une seule ligne du fichier  
- `fichier.readlines()` : lit toutes les lignes et les retourne sous forme de liste

### 2.3. Fermer un fichier
Il est important de fermer le fichier après utilisation :  
```python
fichier.close()
```

## 3. Écrire dans des fichiers texte

### 3.1. Ouvrir un fichier en mode écriture
Pour écrire dans un fichier, on l’ouvre en mode écriture :  
```python
fichier = open('chemin/vers/fichier.txt', 'w')  # 'w' pour écriture
```

### 3.2. Écrire du texte dans un fichier
Utilisez la méthode `write()` pour ajouter du texte :  
```python
fichier.write('Ceci est une ligne de texte.')
```

### 3.3. Ajouter du texte à un fichier existant
Pour ajouter du texte sans écraser le contenu existant, ouvrez le fichier en mode ajout :  
```python
fichier = open('chemin/vers/fichier.txt', 'a')  # 'a' pour ajouter
```

## 4. Travailler avec des fichiers CSV

### 4.1. Qu'est-ce qu'un fichier CSV ?
Un fichier CSV est un fichier texte qui utilise une virgule pour séparer les valeurs.  

### 4.2. Lire un fichier CSV avec `csv`
On utilise le module `csv` pour lire des fichiers CSV :  
```python
import csv
with open('chemin/vers/fichier.csv', newline='') as fichier:
    lecteur = csv.reader(fichier)
    for ligne in lecteur:
        print(ligne)
```

### 4.3. Écrire dans un fichier CSV
Pour écrire dans un fichier CSV :  
```python
import csv
with open('chemin/vers/fichier.csv', mode='w', newline='') as fichier:
    auteur = csv.writer(fichier)
    auteur.writerow(['Colonne1', 'Colonne2'])  # Écrit l'en-tête
    auteur.writerow(['Valeur1', 'Valeur2'])
```

## 5. Gestion des exceptions

### 5.1. Pourquoi gérer les exceptions ?
La gestion des exceptions permet de traiter les erreurs de manière contrôlée, ce qui améliore la robustesse du code.  

### 5.2. Utiliser `try`, `except` et `finally`
La structure de base de gestion des exceptions est :  
```python
try:
    # Code qui peut provoquer une exception
except ExceptionType:
    # Code à exécuter en cas d'exception
finally:
    # Code à exécuter en dernier (optional)
```

### 5.3. Exceptions courantes lors du travail avec des fichiers
Quelques exceptions courantes comprennent :  
- `FileNotFoundError` : levée lorsque le fichier est introuvable  
- `IOError` : levée lors d'une erreur d'entrée/sortie

## 6. Exercices pratiques

### 6.1. Lire un fichier texte et afficher son contenu
### 6.2. Écrire des données dans un fichier texte
### 6.3. Créer et manipuler un fichier CSV
### 6.4. Gérer les exceptions dans les opérations sur les fichiers

## 7. Conclusion

### 7.1. Récapitulatif des concepts abordés
Dans cette formation, nous avons appris comment lire et écrire dans des fichiers texte et CSV, et comment gérer les exceptions.  

### 7.2. Ressources supplémentaires
- [Documentation Python sur les fichiers](https://docs.python.org/fr/3/tutorial/inputoutput.html#reading-and-writing-files)
- [Module CSV](https://docs.python.org/fr/3/library/csv.html)