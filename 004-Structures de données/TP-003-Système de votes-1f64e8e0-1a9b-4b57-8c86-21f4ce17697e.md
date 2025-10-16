# Travail Pratique : Système de Votes

## Objectif
Ce travail pratique a pour but de vous faire manipuler des collections de données en Python à travers un système simple de votes.

## Contexte
Imaginons que nous souhaitons créer un système de vote pour élire un candidat dans une élection. Les utilisateurs doivent pouvoir voter pour leur candidat préféré, et à la fin du scrutin, nous devons déterminer le candidat ayant reçu le plus de votes.

## Instructions
1. **Créer une liste de candidats** : Commencez par créer une liste de candidats. Par exemple :
   ```python
   candidats = ["Alice", "Bob", "Charlie"]
   ```

2. **Collecter les votes** : Demandez à l'utilisateur combien de votes il souhaite effectuer. Ensuite, à chaque vote, demandez à l'utilisateur de choisir un candidat dans la liste.

3. **Stocker les votes** : Utilisez un dictionnaire pour enregistrer le nombre de votes pour chaque candidat. Par exemple :
   ```python
   votes = {"Alice": 0, "Bob": 0, "Charlie": 0}
   ```

4. **Afficher les résultats** : À la fin du scrutin, affichez le nombre total de votes pour chaque candidat, et déterminez le gagnant.

## Exemple de code
Voici un exemple de code pour vous aider à commencer :

```python
# Liste des candidats
candidats = ["Alice", "Bob", "Charlie"]

# Dictionnaire pour stocker les votes
votes = {"Alice": 0, "Bob": 0, "Charlie": 0}

# Collecter les votes
nombre_de_votes = int(input("Combien de votes voulez-vous effectuer ? "))
for i in range(nombre_de_votes):
    vote = input(f"Vote {i + 1}: qui est votre candidat préféré ? ").capitalize()
    if vote in candidats:
        votes[vote] += 1
    else:
        print(f"{vote} n'est pas un candidat valide.")

# Afficher les résultats
print("Résultats des votes :")
for candidat, nombre_de_votes in votes.items():
    print(f"{candidat} : {nombre_de_votes} votes")

# Déterminer le gagnant
gagnant = max(votes, key=votes.get)
print(f"Le gagnant est : {gagnant}")
```

## Corrigé
1. **Création de la liste de candidats** : La liste est correctement créée avec des valeurs valides.
2. **Collecte des votes** : Assurez-vous que l'utilisateur confirme ses choix et qu'il n'y a pas d'erreurs dans les entrées.
3. **Stockage des votes** : Le dictionnaire doit être correctement mis à jour à chaque vote.
4. **Affichage des résultats** : Les résultats doivent être affichés clairement, et le gagnant doit être identifié correctement.

### Note
N'oubliez pas de tester votre code avec différents scénarios pour vous assurer qu'il fonctionne comme prévu.