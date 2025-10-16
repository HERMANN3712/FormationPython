# TP-002 : Générateur de tables de multiplication

## Objectif
Savoir contrôler l’exécution d’un programme avec des conditions et des boucles.

## Description
Dans ce travail pratique, vous allez créer un programme Python qui génère et affiche les tables de multiplication pour un nombre donné. Vous allez utiliser des boucles pour itérer à travers les multiples et conditionner l’affichage de ces multiples.

## Instructions
1. **Demander à l'utilisateur un nombre entier positif** dont il souhaite voir la table de multiplication.
2. **Utiliser une boucle `for`** pour parcourir les nombres de 1 à 10.
3. **Pour chaque nombre de 1 à 10,** calculer la multiplication avec le nombre donné.
4. **Afficher le résultat** sous la forme suivante : `nombre x multiplicateur = résultat`.

## Exemple d'exécution
```
Entrez un nombre entier positif : 5

Table de multiplication de 5 :
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

## Corrigé
Voici un exemple de solution possible :

```python
# Demander à l'utilisateur de saisir un nombre
nombre = int(input("Entrez un nombre entier positif : "))

# Afficher la table de multiplication
print(f"Table de multiplication de {nombre} :")

# Boucle pour générer la table de multiplication
for i in range(1, 11):
    resultat = nombre * i
    print(f"{nombre} x {i} = {resultat}")
```

## Conseils
- Pensez à ajouter une condition pour vérifier que l'utilisateur entre un nombre entier positif.
- Vous pouvez également améliorer l'affichage avec des espaces pour un rendu plus esthétique.
