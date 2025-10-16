# Formation Python pour l’administration système

## Cours 001 : Gestion de fichiers

### Objectifs de la formation
- Comprendre les concepts de base de la gestion de fichiers en Python
- Apprendre à manipuler des fichiers (créer, lire, écrire, supprimer)
- Utiliser des bibliothèques Python pour simplifier les opérations sur les fichiers
- Appliquer les connaissances pour automatiser des tâches administratives

### Prérequis
- Connaissance de base de Python (variables, boucles, conditions)

---

## Plan du cours
1. Introduction à la gestion de fichiers en Python
2. Ouverture et fermeture de fichiers
3. Lecture et écriture de fichiers
4. Manipulation avancée des fichiers
5. Gestion des erreurs et exceptions
6. Exemples pratiques
7. Conclusion et ressources complémentaires

---

## 1. Introduction à la gestion de fichiers en Python
La gestion de fichiers est essentielle pour toute forme d’administration système. En Python, l'interaction avec le système de fichiers est simple et intuitive.

### 1.1 Pourquoi utiliser Python pour la gestion de fichiers ?
- Automatisation des tâches répétitives
- Traitement de données volumineuses
- Intégration facilitée avec d’autres outils

---

## 2. Ouverture et fermeture de fichiers
En Python, vous utilisez la fonction `open()` pour ouvrir un fichier et `close()` pour le fermer. 

### 2.1 La fonction open()
- Syntaxe : `open(nom_du_fichier, mode)`  
- Modes d'ouverture :
  - `r` : lecture
  - `w` : écriture (écrase le fichier s'il existe)
  - `a` : ajout (ajoute à la fin du fichier)
  - `b` : binaire (pour les fichiers médias)

### 2.2 Exemple
```python
f = open('exemple.txt', 'r')  
donnees = f.read()  
f.close()
```

---

## 3. Lecture et écriture de fichiers
### 3.1 Lecture d'un fichier
Utilisez les méthodes `read()`, `readline()` ou `readlines()`.

### 3.2 Écriture dans un fichier
Vous pouvez écrire dans des fichiers en utilisant la méthode `write()`.

### 3.3 Exemples
```python
# Lecture
with open('exemple.txt', 'r') as f:
    contenu = f.read()

# Écriture
with open('nouveau_fichier.txt', 'w') as f:
    f.write('Hello, world!')
```

---

## 4. Manipulation avancée des fichiers
### 4.1 Utilisation de bibliothèques
Python inclut des bibliothèques comme `os` et `shutil` pour la manipulation de fichiers et de répertoires.

### 4.2 Exemples d’utilisation
```python
import os
import shutil

# Créer un répertoire
os.makedirs('nouveau_dossier')

# Copier un fichier
shutil.copy('exemple.txt', 'nouveau_dossier/')
```

---

## 5. Gestion des erreurs et exceptions
Il est important de gérer les exceptions lors de la manipulation de fichiers pour éviter les plantages de programme.

### 5.1 Utilisation de try-except
```python
try:
    with open('inexistant.txt', 'r') as f:
        contenu = f.read()
except FileNotFoundError:
    print("Le fichier n'existe pas.")
```

---

## 6. Exemples pratiques
### 6.1 Automatisation de la sauvegarde de fichiers
### 6.2 Traitement de fichiers log
### 6.3 Lecture et écriture CSV avec la bibliothèque `csv`

---

## 7. Conclusion et ressources complémentaires
Dans ce cours, nous avons vu comment gérer des fichiers en Python. Pour aller plus loin, voici quelques ressources:
- [Documentation Python sur les fichiers](https://docs.python.org/3/tutorial/inputoutput.html#reading-and-writing-files)
- [Python Module Index](https://docs.python.org/3/py-modindex.html)
- [Automate the Boring Stuff with Python](https://automatetheboringstuff.com/)