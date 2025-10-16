# Formation : Introduction à Python

## Cours 004 : Entrées/Sorties Utilisateur

### Objectifs de la formation
- Comprendre les concepts d'entrées et de sorties en Python.
- Savoir utiliser les fonctions `input()` et `print()`.
- Manipuler les données saisies par l'utilisateur.

### Plan de la formation
1. **Introduction aux entrées/sorties**  
   - Définition d'entrées et de sorties  
   - Importance des entrées/sorties dans la programmation interactive

2. **La fonction `print()`**  
   - Syntaxe de `print()`  
   - Affichage de chaînes de caractères  
   - Affichage de variables  
   - Formattage de chaînes avec `f-strings`

3. **La fonction `input()`**  
   - Syntaxe de `input()`  
   - Saisie de données par l'utilisateur  
   - Types de données et conversion  
   - Exemples pratiques

4. **Manipulation des données d'entrée**  
   - Validation des entrées utilisateur  
   - Utilisation de boucles pour la répétition d'entrées

5. **Gestion des erreurs**  
   - Introduction aux exceptions  
   - Essayer/Attraper (try/except) pour gérer les erreurs d'entrée

6. **Exemples pratiques**  
   - Application : un convertisseur de température  
   - Application : un questionnaire simple

7. **Conclusion et exercices**  
   - Révision des concepts clés  
   - Exercices pratiques pour renforcer les acquis

---

### Détails de chaque section

#### 1. Introduction aux entrées/sorties
Les entrées et sorties (E/S) sont des opérations essentielles dans la programmation qui permettent à un programme d'interagir avec l'utilisateur. 

#### 2. La fonction `print()`
La fonction `print()` est utilisée pour afficher des informations à l'écran. Elle peut afficher des chaînes de caractères, des nombres, et même des résultats de calculs.  
**Exemple :**  
```python
print("Bonjour, monde!")
```

#### 3. La fonction `input()`
La fonction `input()` permet de récupérer des données entrées par l'utilisateur. Par défaut, elle retourne une chaîne de caractères.  
**Exemple :**  
```python
nom = input("Quel est ton nom ? ")
print(f"Bonjour, {nom}!")
```

#### 4. Manipulation des données d'entrée
Les données saisies par les utilisateurs peuvent être validées et converties selon les besoins.  
**Validation :**  
Vous pouvez utiliser des boucles pour demander une saisie jusqu'à ce qu'une entrée valide soit fournie.

#### 5. Gestion des erreurs
Lorsque l'utilisateur entre des données incorrectes, cela peut causer des erreurs. Utiliser `try/except` pour gérer cela.  
**Exemple :**  
```python
try:
    age = int(input("Quel âge as-tu ? "))
except ValueError:
    print("Ce n'est pas un âge valide!")
```  

#### 6. Exemples pratiques
- **Convertisseur de température** : Demander à l'utilisateur une température en Celsius et retourner la température en Fahrenheit.
- **Questionnaire simple** : Poser trois questions et afficher les réponses après la saisie de l'utilisateur.

---

### Exercices pratiques
1. Créez un programme qui demande à l'utilisateur de saisir son nom et son âge, puis affiche un message personnalisé.
2. Établissez un convertisseur de monnaie entre Euro et Dollar.

### Conclusion
Ce cours sur les entrées et sorties en Python vous a permis de comprendre comment interagir avec l'utilisateur. Pratiquez en réalisant des programmes interactifs!