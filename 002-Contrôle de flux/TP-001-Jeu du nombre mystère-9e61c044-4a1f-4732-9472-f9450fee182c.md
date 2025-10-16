# Travail Pratique : Jeu du Nombre Mystère

## Objectif
L'objectif de ce travail pratique est d'apprendre à contrôler l'exécution d'un programme avec des conditions et des boucles en Python.

## Description
Dans cet exercice, vous allez créer un jeu où l'utilisateur doit deviner un nombre mystère choisi par l'ordinateur. L'ordinateur générera un nombre aléatoire entre 1 et 100, et l'utilisateur devra entrer ses suppositions jusqu'à ce qu'il trouve le bon nombre.

## Instructions
1. Importez le module `random` pour générer un nombre aléatoire.
2. Générez un nombre mystérieux entre 1 et 100.
3. Demandez à l'utilisateur de deviner le nombre.
4. Utilisez une boucle pour continuer à demander des suppositions tant que l'utilisateur n'a pas trouvé le bon nombre.
5. Utilisez des conditions pour donner des indices à l'utilisateur :
   - Si le nombre deviné est plus petit que le nombre mystère, affichez "Trop petit!"
   - Si le nombre deviné est plus grand que le nombre mystère, affichez "Trop grand!"
6. Lorsque l'utilisateur trouve le nombre, affichez un message de félicitations et le nombre de tentatives.

## Exigences
- Utiliser des boucles `while`.
- Utiliser des instructions `if` pour les conditions.
- Documenter le code avec des commentaires.

## Correction
Voici une solution possible au travail pratique :

```python
import random

# Générer un nombre mystère entre 1 et 100
nombre_mystere = random.randint(1, 100)

tentatives = 0

print("Bienvenue au jeu du nombre mystère!")

while True:
    proposition = int(input("Devinez le nombre (entre 1 et 100) : "))
    tentatives += 1
    
    if proposition < nombre_mystere:
        print("Trop petit!")
    elif proposition > nombre_mystere:
        print("Trop grand!")
    else:
        print(f"Félicitations! Vous avez trouvé le nombre {nombre_mystere} en {tentatives} tentatives.")
        break
```

### Explications
- Le module `random` est importé pour générer le nombre mystère.
- Une boucle `while` est utilisée pour continuer à demander des suppositions tant que l'utilisateur n'a pas trouvé le bon nombre.
- Les instructions `if`, `elif`, et `else` contrôlent le flux du programme en fonction de la supposition de l'utilisateur.