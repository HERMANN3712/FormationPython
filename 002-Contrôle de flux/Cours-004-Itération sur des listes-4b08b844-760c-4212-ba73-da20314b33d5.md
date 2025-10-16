# Formation Python : Contrôle de flux

## Cours 004 : Itération sur des listes

### Introduction
L'itération est une notion essentielle en programmation qui nous permet de répéter des actions jusqu'à ce qu'une condition soit remplie. Dans ce cours, nous allons explorer diverses méthodes pour itérer sur des listes en Python, en utilisant des boucles `for`, des boucles `while`, et la compréhension de liste.

### Plan de la formation
1. **Introduction aux listes en Python**  
   1.1. Définition
   1.2. Création d'une liste
   1.3. Accès aux éléments d'une liste
2. **Boucles `for`**  
   2.1. Syntaxe de la boucle `for`
   2.2. Exemples d'utilisation
   2.3. Utilisation de `range()` avec `for`
3. **Boucles `while`**  
   3.1. Syntaxe de la boucle `while`
   3.2. Exemples d'utilisation
   3.3. Comparaison entre `for` et `while`
4. **Compréhension de liste**  
   4.1. Définition et syntaxe
   4.2. Exemples de compréhension de liste
   4.3. Applications pratiques
5. **Exercices pratiques**  
   5.1. Itérer sur une liste de nombres
   5.2. Itérer sur une liste de chaînes de caractères
   5.3. Créer une nouvelle liste avec compréhension
6. **Conclusion**  
   6.1. Résumé des concepts
   6.2. Ressources supplémentaires

### 1. Introduction aux listes en Python

Les listes en Python sont des structures de données qui peuvent contenir une séquence d'éléments, qui peuvent être de types différents. Elles sont créées en plaçant les éléments entre crochets `[ ]` et en les séparant par des virgules.

#### 1.1. Définition
Une liste est un conteneur qui peut contenir différents types d'objets : entiers, chaînes de caractères, objets, ou même d'autres listes.

#### 1.2. Création d'une liste
```python
ma_liste = [1, 2, 3, 4, 5]
```

#### 1.3. Accès aux éléments d'une liste
Pour accéder à un élément dans une liste, nous utilisons l'index. Notez que les index commencent à 0.
```python
premier_element = ma_liste[0]  # 1
```

### 2. Boucles `for`
La boucle `for` est utilisée pour itérer sur les éléments d'une séquence, comme une liste.

#### 2.1. Syntaxe de la boucle `for`
```python
for element in ma_liste:
    print(element)
```

#### 2.2. Exemples d'utilisation
Voici un exemple qui affiche chaque élément de la liste :
```python
ma_liste = ['a', 'b', 'c']
for lettre in ma_liste:
    print(lettre)
```
#### 2.3. Utilisation de `range()` avec `for`
Pour itérer à travers une série de nombres, `range()` est souvent utilisé.
```python
for i in range(5):
    print(i)
```

### 3. Boucles `while`
La boucle `while` continue tant qu'une condition est vraie.

#### 3.1. Syntaxe de la boucle `while`
```python
compteur = 0
while compteur < 5:
    print(compteur)
    compteur += 1
```

#### 3.2. Exemples d'utilisation
Une boucle `while` peut être utilisée pour ajouter des éléments à une liste jusqu'à ce qu'une condition soit remplie.

#### 3.3. Comparaison entre `for` et `while`
Utilisez `for` pour un nombre fixe d'itérations et `while` lorsque le nombre d'itérations ne peut pas être prédéfini.

### 4. Compréhension de liste
La compréhension de liste offre une manière concise d'itérer et de créer des listes.

#### 4.1. Définition et syntaxe
```python
new_list = [expression for item in iterable]
```
#### 4.2. Exemples de compréhension de liste
```python
carres = [x**2 for x in range(10)]
```
#### 4.3. Applications pratiques
Créer des listes filtrées ou transformées de manière concise.

### 5. Exercices pratiques
#### 5.1. Itérer sur une liste de nombres
Écrire un code qui imprime les carrés des nombres d'une liste.  
#### 5.2. Itérer sur une liste de chaînes de caractères
Écrire un code qui affiche chaque mot d'une phrase.
#### 5.3. Créer une nouvelle liste avec compréhension
Créer une liste des cubes des nombres de 0 à 9.

### 6. Conclusion
#### 6.1. Résumé des concepts
Nous avons vu différentes manières d'itérer sur des listes en Python, notamment avec `for`, `while`, et la compréhension de liste.
#### 6.2. Ressources supplémentaires
- Documentation Python officielle
- Tutoriels de Python sur Real Python

---

**Fin de la formation**

