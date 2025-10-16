# Formation Python : Structures de données

## Introduction
Dans cette formation, nous allons explorer quatre types fondamentaux de structures de données en Python : les listes, les tuples, les ensembles (sets) et les dictionnaires. Nous couvrirons leurs caractéristiques, leurs utilisations et des exemples pratiques pour illustrer leurs fonctions.

## Plan de la formation
1. [Listes](#listes)
   - Définition
   - Création
   - Méthodes courantes
   - Exemples

2. [Tuples](#tuples)
   - Définition
   - Création
   - Avantages par rapport aux listes
   - Exemples

3. [Sets](#sets)
   - Définition
   - Création
   - Opérations sur les sets
   - Exemples

4. [Dictionnaires](#dictionnaires)
   - Définition
   - Création
   - Méthodes courantes
   - Exemples

---

## 1. Listes

### Définition
Les listes en Python sont des collections ordonnées et modifiables d'éléments. Elles peuvent contenir des éléments de types différents, y compris d'autres listes.

### Création
Pour créer une liste, on utilise des crochets `[]` :  
```python
ma_liste = [1, 2, 3, 'quatre', 5.0]
```

### Méthodes courantes
Quelques méthodes utiles pour les listes :
- `append()`: Ajoute un élément à la fin de la liste
- `remove()`: Supprime le premier élément correspondant à la valeur donnée
- `pop()`: Supprime et retourne l'élément à l'index donné
- `sort()`: Trie la liste en place

### Exemples
```python
# Exemple de liste et méthodes
ma_liste = [3, 1, 4, 1, 5, 9]
ma_liste.append(2)
ma_liste.sort()
print(ma_liste)  # Output : [1, 1, 2, 3, 4, 5, 9]
```

---

## 2. Tuples

### Définition
Un tuple est une collection ordonnée et immuable d'éléments. Une fois créé, on ne peut pas modifier un tuple.

### Création
On utilise des parenthèses `()` pour créer un tuple :  
```python
tuile = (1, 2, 3)
```

### Avantages par rapport aux listes
- Les tuples sont plus légers en termes de mémoire.
- Ils peuvent être utilisés comme clés dans des dictionnaires alors que les listes ne le peuvent pas.

### Exemples
```python
# Exemple de tuple
mon_tuple = (1, 'deux', 3.0)
print(mon_tuple[1])  # Output : 'deux'
```

---

## 3. Sets

### Définition
Un set est une collection non ordonnée d'éléments uniques. Ils sont utiles pour éliminer les doublons dans une liste.

### Création
On utilise des accolades `{}` pour créer un set :  
```python
mon_set = {1, 2, 3, 4, 4}
```

### Opérations sur les sets
- `add()`: Ajoute un élément au set
- `remove()`: Supprime un élément du set
- `union()`: Retourne la combinaison de deux sets

### Exemples
```python
# Exemple de set
mon_set = {1, 2, 3, 3}
mon_set.add(4)
print(mon_set)  # Output : {1, 2, 3, 4}
```

---

## 4. Dictionnaires

### Définition
Les dictionnaires sont des collections non ordonnées d'éléments sous forme de paires clé-valeur. Ils permettent un accès rapide aux données.

### Création
On utilise des accolades `{}` et deux-points `:` pour créer un dictionnaire :  
```python
dico = {'clé1': 'valeur1', 'clé2': 'valeur2'}
```

### Méthodes courantes
- `get()`: Retourne la valeur pour une clé donnée
- `keys()`: Retourne une vue des clés du dictionnaire
- `values()`: Retourne une vue des valeurs du dictionnaire

### Exemples
```python
# Exemple de dictionnaire
dico = {'nom': 'Alice', 'âge': 25}
print(dico['nom'])  # Output : 'Alice'
```

---

## Conclusion
Dans cette formation, nous avons exploré les principales structures de données en Python : listes, tuples, sets et dictionnaires. Chacun a ses propres caractéristiques et cas d'utilisation. La bonne compréhension de ces structures est essentielle pour écrire un code Python efficace.