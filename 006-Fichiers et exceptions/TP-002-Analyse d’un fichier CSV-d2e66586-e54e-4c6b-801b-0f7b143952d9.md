# Travail Pratique : Analyse d’un fichier CSV

## Objectif

L'objectif de ce travail pratique est de vous familiariser avec la lecture et l'écriture de fichiers CSV, ainsi que la gestion des erreurs potentielles lors de ces opérations.

## Prérequis

- Connaissance de base en Python
- Bibliothèque `csv` importée (partie de la bibliothèque standard)

## Description du TP

Vous allez travailler sur un fichier CSV contenant des informations sur des étudiants. Le fichier a la structure suivante :

```
ID, Nom, Age, Note
1, Alice, 22, 85
2, Bob, 21, 75
3, Charlie, 23, 90
4, David, 20, 60
5, Eva, 22, 95
```

### Étapes à suivre

1. **Créer un fichier CSV** :
   - Écrivez un script qui crée un fichier CSV avec les données ci-dessus.

2. **Lire et afficher le contenu du fichier CSV** :
   - Écrivez un script qui lit le fichier créé et affiche son contenu.

3. **Gérer les exceptions** :
   - Gérez les exceptions possibles lors de l'ouverture et de la lecture du fichier (ex: `FileNotFoundError`, `IOError`). Ajoutez des messages d'erreur appropriés.

### Exercice 1 : Créer un fichier CSV

```python
import csv

def ecrire_fichier_csv(nom_fichier):
    data = [
        ['ID', 'Nom', 'Age', 'Note'],
        [1, 'Alice', 22, 85],
        [2, 'Bob', 21, 75],
        [3, 'Charlie', 23, 90],
        [4, 'David', 20, 60],
        [5, 'Eva', 22, 95]
    ]
    try:
        with open(nom_fichier, mode='w', newline='') as fichier:
            writer = csv.writer(fichier)
            writer.writerows(data)
            print(f'Fichier {nom_fichier} créé avec succès.')
    except IOError:
        print('Une erreur est survenue lors de l’écriture du fichier.')

# Appel de la fonction
nom_fichier = 'etudiants.csv'
ecrire_fichier_csv(nom_fichier)
```

### Exercice 2 : Lire et afficher le contenu du fichier CSV

```python
import csv

def lire_fichier_csv(nom_fichier):
    try:
        with open(nom_fichier, mode='r') as fichier:
            lecteur = csv.reader(fichier)
            for ligne in lecteur:
                print(ligne)
    except FileNotFoundError:
        print(f'Erreur : le fichier {nom_fichier} n\'existe pas.')
    except IOError:
        print('Une erreur est survenue lors de la lecture du fichier.')

# Appel de la fonction
lire_fichier_csv(nom_fichier)
```

## Corrigé

- **Exercice 1** : Le fichier CSV est créé avec succès si aucune erreur ne se produit.
- **Exercice 2** : Le contenu du fichier est affiché ligne par ligne. Les messages d'erreur apparaissent si le fichier n'est pas trouvé ou en cas d'autres erreurs d'entrée/sortie.

### Conseils

- Assurez-vous que le fichier est bien créé avant d'essayer de le lire.
- Gérez toutes les exceptions possibles pour éviter que votre programme ne se bloque.