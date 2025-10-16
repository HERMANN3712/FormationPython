# Formation : Fonctions et Portée en Python

## Cours 002 : Paramètres et Retours

---

### Objectif de la formation
Apprendre à manipuler les fonctions en Python à travers la compréhension des paramètres et des valeurs de retour.

### Plan de la formation
1. Introduction aux fonctions
    - Qu'est-ce qu'une fonction ?
    - Pourquoi utiliser des fonctions ?

2. Définir une fonction en Python
    - Syntaxe de base
    - Exemples de fonctions

3. Paramètres des fonctions
    - Paramètres positionnels
    - Paramètres nommés
    - Valeurs par défaut
    - Paramètres variables

4. Valeurs de retour
    - Utilisation de l'instruction `return`
    - Valeurs de retour multiples
    - Exemple de fonction retournant plusieurs valeurs

5. Instance pratique
    - Exercices
    - Évaluation des exercices

6. Conclusion
    - Récapitulatif
    - Questions et réponses

---

## 1. Introduction aux fonctions

### Qu'est-ce qu'une fonction ?
Une fonction est un bloc de code qui ne s'exécute que lorsqu'il est appelé. Elle peut recevoir des données, faire des calculs ou effectuer des actions, puis éventuellement renvoyer un résultat.

### Pourquoi utiliser des fonctions ?
- Réutilisation du code : Écrire une fois, utiliser plusieurs fois.
- Lisibilité du code : Rendre le code plus clair et structuré.
- Modularité : Diviser le code en petits morceaux gérables.

---

## 2. Définir une fonction en Python

### Syntaxe de base
```python
def nom_de_la_fonction(param1, param2):
    # Corps de la fonction
    return valeur_à_retourner
```

### Exemples de fonctions
```python
# Fonction qui additionne deux nombres

def additionner(a, b):
    return a + b

resultat = additionner(5, 3)
print(resultat)  # Affiche 8
```

---

## 3. Paramètres des fonctions

### Paramètres positionnels
Les paramètres positionnels sont attribués aux arguments en fonction de leur position.

### Paramètres nommés
Les paramètres nommés sont spécifiés par leur nom. Cela permet de passer les arguments dans n'importe quel ordre.

### Valeurs par défaut
Vous pouvez définir des valeurs par défaut pour des paramètres. Cela permet d'appeler la fonction sans spécifier ces paramètres.

### Paramètres variables
```python
def afficher_noms(*noms):
    for nom in noms:
        print(nom)
```

---

## 4. Valeurs de retour

### Utilisation de l'instruction `return`
L'instruction `return` permet à une fonction de renvoyer une valeur. Sans `return`, la fonction renvoie `None`.

### Valeurs de retour multiples
Une fonction peut retourner plusieurs valeurs sous forme de tuple.
```python
def calculer(a, b):
    somme = a + b
    difference = a - b
    return somme, difference

resultat = calculer(5, 3)
print(resultat)  # Affiche (8, 2)
```

---

## 5. Instance pratique

### Exercices
1. Créez une fonction qui calcule le carré d'un nombre.
2. Écrivez une fonction qui prend plusieurs chaînes de caractères et les concatène.

### Évaluation des exercices
- Discussion en groupe sur les solutions proposées.
- Retour sur les erreurs et les bonnes pratiques.

---

## 6. Conclusion

### Récapitulatif
Dans ce cours, nous avons exploré les conceptions essentielles des paramètres et des valeurs de retour dans les fonctions Python.

### Questions et réponses
Encouragez les participants à poser des questions pour clarifier les concepts abordés.