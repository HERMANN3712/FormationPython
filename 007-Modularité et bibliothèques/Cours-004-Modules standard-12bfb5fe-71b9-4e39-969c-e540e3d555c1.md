# Formation Python : Modularité et bibliothèques  
## Module 004 : Modules standard  

### Objectifs de la formation  
- Comprendre le concept de modularité en Python.  
- Découvrir les modules standard inclus dans Python.  
- Savoir comment utiliser et créer des modules.  

### Plan de la formation  
1. Introduction  
   - Présentation de Python et de son écosystème  
   - Importance de la modularité  
 
2. Comprendre les modules  
   - Définition d'un module  
   - Utilisation des modules en Python  
   - Structure d'un module  

3. Les modules standard de Python  
   - Présentation des modules standard  
   - Exemple d'utilisation de certains modules  
     - `os` : Interaction avec le système d'exploitation  
     - `sys` : Gestion des arguments de la ligne de commande  
     - `math` : Fonctions mathématiques  
     - `datetime` : Gestion des dates et heures  
     - `random` : Génération de nombres aléatoires  
  
4. Création de modules personnalisés  
   - Comment créer un module  
   - Organisation du code  
   - Importation de modules  
   - Exemples de modules personnalisés  
 
5. Utilisation de bibliothèques tierces  
   - Introduction à l'utilisation de bibliothèques tierces  
   - Installation et gestion des bibliothèques avec `pip`  
   - Exemples d'utilisation de bibliothèques populaires  
     - `requests` : Gestion des requêtes HTTP  
     - `numpy` : Calcul numérique  
     - `pandas` : Manipulation de données  
 
6. Conclusion  
   - Récapitulatif des concepts abordés  
   - Ressources supplémentaires pour aller plus loin  

---  

### Détails du contenu  

## 1. Introduction  
Python est un langage de programmation polyvalent, populaire pour sa simplicité et sa lisibilité. L'un de ses atouts majeurs est la modularité, qui permet d'organiser le code en fichiers séparés appelés modules. Cela améliore la lisibilité, la réutilisabilité et la maintenance du code.  

## 2. Comprendre les modules  
Un **module** en Python est un fichier contenant du code Python. Ce code peut inclure des fonctions, des classes et des variables. L'utilisation de modules permet de séparer le code en unités logiques.  

### Utilisation des modules  
En Python, l'importation d'un module se fait grâce à l'instruction `import`. Par exemple :  
```python  
import math  
print(math.sqrt(16))  # Affiche 4.0  
```  
### Structure d'un module  
Un module peut contenir plusieurs composants :  
- Fonctions  
- Classes  
- Variables  

## 3. Les modules standard de Python  
Python vient avec un ensemble de modules standard qui fournissent des fonctionnalités essentielles. Voici quelques-uns des modules les plus couramment utilisés :  

### 3.1 Module `os`  
Le module `os` permet d'interagir avec le système d'exploitation. Par exemple :  
```python  
import os  
print(os.getcwd())  # Affiche le répertoire de travail actuel  
```  
### 3.2 Module `sys`  
Le module `sys` fournit des fonctions et des variables qui interagissent avec l'interpréteur Python. Exemple d'utilisation :  
```python  
import sys  
print(sys.argv)  # Affiche la liste des arguments de la ligne de commande  
```  
### 3.3 Module `math`  
Le module `math` inclut des fonctions mathématiques telles que `sqrt`, `sin`, et `cos`. Exemple :  
```python  
import math  
print(math.pi)  # Affiche la valeur de pi  
```  
### 3.4 Module `datetime`  
Le module `datetime` permet de travailler avec les dates et heures. Exemple :  
```python  
from datetime import datetime  
now = datetime.now()  
print(now)  # Affiche la date et l'heure actuelles  
```  
### 3.5 Module `random`  
Le module `random` permet de générer des nombres aléatoires. Exemple :  
```python  
import random  
print(random.randint(1, 10))  # Affiche un nombre aléatoire entre 1 et 10  
```  

## 4. Création de modules personnalisés  
Pour créer votre propre module, il suffit de créer un fichier Python (avec l'extension .py). Par exemple, un fichier `mon_module.py` pourrait contenir :  
```python  
def ma_fonction():  
    return "Bonjour, monde !"  
```  
### Importation de modules  
Vous pouvez importer vos modules de la même manière que vous le feriez avec les modules standard :  
```python  
import mon_module  
print(mon_module.ma_fonction())  
```  

## 5. Utilisation de bibliothèques tierces  
Une fois que vous êtes familiarisé avec les modules, vous pouvez également utiliser des bibliothèques tierces. Ces bibliothèques étendent vos capacités avec des fonctionnalités supplémentaires.  
### Installation avec `pip`  
`pip` est l'outil de gestion des paquets de Python. Vous pouvez installer une bibliothèque tierce avec la commande suivante :  
```bash  
pip install requests  
```  
### Exemples de bibliothèques  
- **Requests** : pour les appels HTTP, très utilisé en développement web.  
- **NumPy** : pour les calculs mathématiques complexes.  
- **Pandas** : pour la manipulation et l'analyse de données.  

## 6. Conclusion  
La modularité est essentielle pour écrire du code Python propre et maintenable. En utilisant les modules standard et en créant vos propres modules, vous pouvez structurer votre code de manière efficace. N'oubliez pas d'explorer les bibliothèques tierces pour étendre encore davantage vos capacités.  

### Ressources supplémentaires  
- [Documentation officielle de Python](https://docs.python.org/3/)  
- [Real Python](https://realpython.com/)  
- [GeeksforGeeks](https://www.geeksforgeeks.org/python-programming-language/)  

---  

Merci de votre attention !  
