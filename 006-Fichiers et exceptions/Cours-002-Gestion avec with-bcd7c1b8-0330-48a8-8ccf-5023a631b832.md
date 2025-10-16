# Formation Python: Fichiers et Exceptions

## Cours 002: Gestion avec `with`

### Objectifs de la formation
- Comprendre le principe de la gestion de contextes en Python.
- Apprendre à utiliser le mot-clé `with` pour simplifier la gestion des ressources.
- Explorer les avantages de l'utilisation de `with` pour les fichiers et autres ressources.

### Plan de la formation
1. Introduction à la gestion de contextes
   - Qu'est-ce qu'un contexte en Python ?
   - Importance de la gestion des ressources.

2. Le mot-clé `with`
   - Syntaxe de base.
   - Comparaison avec l'approche traditionnelle.

3. Utilisation de `with` avec les fichiers
   - Lecture d'un fichier.
   - Écriture dans un fichier.
   - Syntaxe avancée avec plusieurs fichiers.

4. Gestion des exceptions avec `with`
   - Traiter les exceptions lors de l'utilisation de `with`.
   - Exemples de gestion des erreurs.

5. Créer son propre gestionnaire de contexte
   - Utiliser la méthode `__enter__` et `__exit__`.
   - Exemples pratiques.

6. Exemples d'utilisation de `with`
   - Lecture et écriture de fichiers CSV.
   - Gestion de connexions à des bases de données.

7. Conclusion
   - Résumé des points clés.
   - Questions et réponses.

### Détails du contenu

#### 1. Introduction à la gestion de contextes
En Python, un contexte représente un environnement dans lequel certaines opérations peuvent être effectuées sans avoir à se préoccuper de la gestion des ressources de manière explicite. Cela inclut l'utilisation de fichiers, de connexions réseau, et bien d'autres.

#### 2. Le mot-clé `with`
Le mot-clé `with` permet de simplifier le code lorsqu'il s'agit de gérer des ressources. Par exemple, au lieu d'ouvrir un fichier, d'effectuer des opérations, puis de le fermer, `with` gère automatiquement la fermeture du fichier.

**Exemple :**
```python
with open('exemple.txt', 'r') as fichier:
    contenu = fichier.read()
    print(contenu)
```

#### 3. Utilisation de `with` avec les fichiers
L'utilisation de `with` pour les fichiers permet d'éviter les fuites de ressources. Voici comment cela fonctionne :

**Lecture :**
```python
with open('exemple.txt', 'r') as fichier:
    contenu = fichier.read()
```

**Écriture :**
```python
with open('exemple.txt', 'w') as fichier:
    fichier.write('Bonjour, monde !')
```

#### 4. Gestion des exceptions avec `with`
Lorsqu'on utilise `with`, il est essentiel de comprendre comment gérer les exceptions qui peuvent survenir.

**Exemple d'exception :**
```python
try:
    with open('exemple.txt', 'r') as fichier:
        contenu = fichier.read()
except FileNotFoundError:
    print('Le fichier n existe pas')
```

#### 5. Créer son propre gestionnaire de contexte
Il est possible de créer des gestionnaires de contexte personnalisés en définissant les méthodes `__enter__` et `__exit__`. Voici un exemple :

```python
class MonContexte:
    def __enter__(self):
        print('Entrée dans le contexte')
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        print('Sortie du contexte')

with MonContexte():
    print('À l intérieur du contexte')
```

#### 6. Exemples d'utilisation de `with`
En plus des fichiers, `with` est également utilisé pour gérer les connexions aux bases de données, les threads, et bien d'autres ressources.

**Exemple de connexion à une base de données :**
```python
import sqlite3

with sqlite3.connect('base_de_donnees.db') as conn:
    cursor = conn.cursor()
    cursor.execute('SELECT * FROM table')
    results = cursor.fetchall()
```

#### 7. Conclusion
L'utilisation de `with` en Python est essentielle pour gérer les ressources de manière efficace et sûre. Cela réduit le risque d'erreurs liées à la gestion des fichiers et autres ressources. N'hésitez pas à poser des questions pour approfondir vos connaissances sur ce sujet.