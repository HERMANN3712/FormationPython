# Formation Python : Modularité et bibliothèques

## Introduction
Cette formation aborde les concepts de modularité en Python, en se concentrant sur l'utilisation de modules et de packages. La modularité est essentielle pour structurer le code de manière efficace et le rendre plus lisible et réutilisable.

## Objectifs de la formation  
À l'issue de cette formation, les participants seront capables de :  
- Comprendre le concept de modules en Python  
- Créer et utiliser des modules  
- Comprendre la notion de packages et leur utilité  
- Structurer un projet Python à l'aide de packages  
- Gérer des dépendances avec les fichiers `requirements.txt`

## Plan de la formation  
1. **Introduction aux modules**  
   - Qu'est-ce qu'un module ?  
   - Pourquoi utiliser des modules ?  
   - Création d'un module  
   - Importation d'un module  
   - Les capacités d'importation  
   - Exercices pratiques

2. **Création et utilisation de modules**  
   - Structure d'un module  
   - Fonctions et variables dans un module  
   - Modulariser un projet  
   - Exemples pratiques  
   - Exercices pratiques

3. **Introduction aux packages**  
   - Qu'est-ce qu'un package ?  
   - Différence entre un module et un package  
   - Création d'un package  
   - Structure d'un package  
   - Utilisation d'un package  
   - Exercices pratiques

4. **Gérer les dépendances**  
   - Introduction à `requirements.txt`  
   - Comment créer et utiliser un fichier `requirements.txt`  
   - Exemples de gestion des dépendances  
   - Exercices pratiques

5. **Bonnes pratiques de modularité**  
   - Organisation du code  
   - Documentation des modules et des packages  
   - Tests unitaires  
   - Gestion des versions  
   - Conclusion

## Détails des sections

### 1. Introduction aux modules
#### Qu'est-ce qu'un module ?  
Un module est un fichier Python contenant des définitions et des instructions Python. Le fichier d'un module porte l'extension `.py`.

#### Pourquoi utiliser des modules ?  
Les modules permettent de structurer le code, de le rendre réutilisable et plus lisible. Ils facilitent également la collaboration entre développeurs.

#### Création d'un module
Pour créer un module, il suffit de créer un fichier `.py` avec du code Python. Par exemple :
```python
# mon_module.py

def ma_fonction():  
    return "Bonjour depuis le module!"
```

#### Importation d'un module
Pour utiliser un module dans un autre fichier, on utilise l'instruction `import` :
```python
import mon_module
print(mon_module.ma_fonction())
```

#### Les capacités d'importation
Il existe plusieurs façons d'importer un module :  
- `import mon_module`  
- `from mon_module import ma_fonction`  
- `from mon_module import *`

#### Exercices pratiques
- Créez un module avec une fonction qui retourne la somme de deux nombres.
- Importez ce module dans un autre fichier.

### 2. Création et utilisation de modules
#### Structure d'un module
Un module peut contenir des fonctions, des classes, des variables globales, etc. 
Exemple : 
```python
# mon_module.py

PI = 3.14

def cercle_aire(rayon):
    return PI * rayon ** 2
```

#### Modulariser un projet
Modulariser un projet Python implique de diviser le code en plusieurs fichiers/modules en fonction de leur fonctionnalité.

#### Exemples pratiques
Créez un projet qui utilise plusieurs modules pour effectuer différentes tâches.

### 3. Introduction aux packages
#### Qu'est-ce qu'un package ?  
Un package est un ensemble de modules regroupés dans un répertoire. Un fichier `__init__.py` est requis pour marquer un répertoire comme un package.

#### Différence entre un module et un package
Un module est un fichier `.py`, tandis qu'un package est un dossier contenant plusieurs modules.

#### Création d'un package
Pour créer un package, suivez ces étapes :
1. Créez un répertoire.
2. Ajoutez des fichiers `.py` (modules) à l'intérieur.
3. Ajoutez un fichier `__init__.py`.

#### Exercices pratiques
Créez un package avec différents modules pour gérer un catalogue de livres.

### 4. Gérer les dépendances
#### Introduction à `requirements.txt`
Le fichier `requirements.txt` est utilisé pour gérer les dépendances d'un projet Python.

#### Comment créer et utiliser un fichier `requirements.txt`
Utilisez la commande `pip freeze > requirements.txt` pour lister toutes les dépendances d'un projet. 

### 5. Bonnes pratiques de modularité
- Commentez et documentez chaque module et fonction.
- Utilisez des tests unitaires pour vérifier le bon fonctionnement.
- Gérez les versions de vos modules pour maintenir la compatibilité.

## Conclusion
La modularité permet d'écrire un code propre, lisible et réutilisable. En maîtrisant les modules et les packages, les développeurs peuvent créer des applications Python robustes et bien structurées.