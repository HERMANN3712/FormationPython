# Travail Pratique : Analyse de Notes d’Élèves

## Objectif
L'objectif de ce travail pratique est d'apprendre à contrôler l'exécution d'un programme à l'aide de conditions et de boucles en Python. Les étudiants doivent être capables d'analyser les notes d'élèves et de classer les résultats.

## Énoncé
Vous devez écrire un programme qui :
1. **Demande à l'utilisateur** d'entrer le nombre d'élèves.
2. **Pour chaque élève**, demandez à l'utilisateur d'entrer le nom et la note de l'élève.
3. **Calculez la moyenne des notes** et affichez-la.
4. **Affichez** les élèves qui ont obtenu une note supérieure à la moyenne.
5. **Affichez** les élèves qui ont échoué (note < 10).

## Indications
- Utilisez une boucle `for` pour itérer sur le nombre d'élèves.
- Utilisez des conditions `if` pour vérifier les notes.

## Exemple de sortie
```
Entrez le nombre d'élèves: 3
Entrez le nom de l'élève 1: Alice
Entrez la note d'Alice: 15
Entrez le nom de l'élève 2: Bob
Entrez la note de Bob: 8
Entrez le nom de l'élève 3: Carol
Entrez la note de Carol: 12

La moyenne des notes est : 11.67

Élèves au-dessus de la moyenne :
- Alice
- Carol

Élèves ayant échoué :
- Bob
```

## Corrigé
Voici un exemple de solution :

```python
# Demande le nombre d'élèves
nombre_eleves = int(input("Entrez le nombre d'élèves: "))

notes = []

for i in range(nombre_eleves):
    nom = input(f"Entrez le nom de l'élève {i + 1}: ")
    note = float(input(f"Entrez la note de {nom}: "))
    notes.append((nom, note))

# Calcule la moyenne
moyenne = sum(note for nom, note in notes) / nombre_eleves
print(f"La moyenne des notes est : {moyenne:.2f}")

# Affiche les élèves au-dessus de la moyenne
print("\nÉlèves au-dessus de la moyenne :")
for nom, note in notes:
    if note > moyenne:
        print(f"- {nom}")

# Affiche les élèves ayant échoué
print("\nÉlèves ayant échoué :")
for nom, note in notes:
    if note < 10:
        print(f"- {nom}")
```

## Conclusion
Cet exercice permet de comprendre comment utiliser les structures de contrôle en Python pour analyser des données et tirer des conclusions. Les étudiants peuvent être encouragés à modifier le programme pour ajouter d'autres fonctionnalités, comme le classement des élèves par ordre de notes ou la gestion des notes invalides.