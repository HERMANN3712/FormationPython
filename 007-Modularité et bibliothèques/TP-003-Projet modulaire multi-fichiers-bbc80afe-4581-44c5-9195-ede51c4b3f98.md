# Travail Pratique: Projet Modulaire Multi-Fichiers

## Objectif
L'objectif de ce travail pratique est de structurer un projet Python en utilisant des modules et des bibliothèques. Les étudiants vont apprendre à créer un projet modulaire, à organiser le code en plusieurs fichiers, et à utiliser des bibliothèques externes.

## Contexte
Vous allez créer une application simple qui gère une bibliothèque. L'application permettra d'ajouter des livres, de les afficher, et de rechercher des livres par titre ou auteur.

## Étapes à Suivre

### 1. Créer la structure de dossiers
Créez un dossier nommé `bibliotheque`. À l'intérieur, créez les sous-dossiers suivants :
- `models`: pour les classes de données.
- `views`: pour les fonctions d'affichage.
- `controllers`: pour la logique de l'application.
- `tests`: pour les tests unitaires (facultatif).

### 2. Créer le fichier principal
Dans le dossier `bibliotheque`, créez un fichier `main.py`. Ce fichier servira de point d'entrée pour votre application.

### 3. Modèle de données
Dans le dossier `models`, créez un fichier `livre.py`. Ce fichier contiendra la classe `Livre` qui aura les propriétés suivantes :
- `titre`
- `auteur`
- `annee_de_publication`

#### Exemple de code:
```python
class Livre:
    def __init__(self, titre, auteur, annee_de_publication):
        self.titre = titre
        self.auteur = auteur
        self.annee_de_publication = annee_de_publication
```

### 4. Fonctions d'affichage
Dans le dossier `views`, créez un fichier `affichage.py`. Ce fichier contiendra des fonctions pour afficher les livres.

#### Exemple de code:
```python
from models.livre import Livre

def afficher_livre(livre):
    print(f'Titre: {livre.titre}, Auteur: {livre.auteur}, Année: {livre.annee_de_publication}')
```

### 5. Logique de l'application
Dans le dossier `controllers`, créez un fichier `bibliotheque_controller.py`. Ce fichier contiendra des fonctions pour gérer la liste des livres.

#### Exemple de code:
```python
from models.livre import Livre
from views.affichage import afficher_livre

class Bibliotheque:
    def __init__(self):
        self.livres = []

    def ajouter_livre(self, titre, auteur, annee):
        livre = Livre(titre, auteur, annee)
        self.livres.append(livre)

    def afficher_livres(self):
        for livre in self.livres:
            afficher_livre(livre)
```

### 6. Intégration dans `main.py`
Dans le fichier `main.py`, importez le controller et créez une instance de la bibliothèque. Ajoutez quelques livres et affichez-les.

#### Exemple de code:
```python
from controllers.bibliotheque_controller import Bibliotheque

if __name__ == '__main__':
    biblio = Bibliotheque()
    biblio.ajouter_livre('1984', 'George Orwell', 1949)
    biblio.ajouter_livre('Le Petit Prince', 'Antoine de Saint-Exupéry', 1943)
    biblio.afficher_livres()
```

### 7. Tester le projet
Exécutez `main.py` pour voir si le projet fonctionne comme prévu. Vous devriez voir une liste des livres ajoutés s'afficher dans la console.

## Corrigé
1. Vérifiez que la structure des fichiers est conforme à la description.
2. Les classes et les fonctions doivent être dans les fichiers corrects avec les importations appropriées.
3. Assurez-vous que l'affichage des livres fonctionne correctement.

## Conclusion
Ce travail pratique illustre comment organiser un projet Python en modules et montrer l'utilisation de classes et de fonctions dans des fichiers séparés. En suivant ces étapes, les étudiants apprendront à mieux structurer leur code et à réutiliser des composants dans différents contextes.