# Formation sur la Programmation Orientée Objet en Python

## Objectifs de la Formation
- Comprendre les concepts de base de la programmation orientée objet (POO).
- Maîtriser les principes d'encapsulation, d'héritage et de polymorphisme.
- Être capable d'appliquer ces concepts dans des projets Python.

## Plan de la Formation

### Introduction à la POO
- Qu'est-ce que la programmation orientée objet?
- Importance et avantages de la POO.

### Encapsulation
#### Définition
L'encapsulation est un principe qui consiste à restreindre l'accès direct à certains composants d'un objet et à protéger son état interne.

#### Objectifs de l'encapsulation
- Protéger les données.
- Réduire la complexité.
- Favoriser la modularité.

#### Implémentation en Python
```python
class CompteBancaire:
    def __init__(self, solde=0):
        self.__solde = solde  # Attribut privé

    def deposer(self, montant):
        if montant > 0:
            self.__solde += montant

    def retirer(self, montant):
        if 0 < montant <= self.__solde:
            self.__solde -= montant

    def afficher_solde(self):
        return self.__solde
```

#### Exemples d'utilisation
```python
compte = CompteBancaire(100)
compte.deposer(50)
print(compte.afficher_solde())  # Affiche 150
compte.retirer(30)
print(compte.afficher_solde())  # Affiche 120
```

### Héritage
#### Définition
L'héritage est un mécanisme qui permet de créer une nouvelle classe à partir d'une classe existante.

#### Objectifs de l'héritage
- Favoriser la réutilisation du code.
- Établir des relations entre les objets.

#### Types d'héritage
- Héritage simple
- Héritage multiple

#### Implémentation en Python
```python
class Animal:
    def parler(self):
        return "Je fais des bruits"

class Chien(Animal):
    def parler(self):
        return "Woof!"

class Chat(Animal):
    def parler(self):
        return "Meow!"
```

#### Exemples d'utilisation
```python
mon_chien = Chien()
print(mon_chien.parler())  # Affiche Woof!
mon_chat = Chat()
print(mon_chat.parler())  # Affiche Meow!
```

### Polymorphisme
#### Définition
Le polymorphisme permet d'utiliser une méthode de la même manière sur des objets de différents types.

#### Objectifs du polymorphisme
- Faciliter l'extension du système.
- Simplifier l'utilisation des classes.

#### Implémentation en Python
```python
class Oiseau:
    def voler(self):
        return "L'oiseau vole"

class Avion:
    def voler(self):
        return "L'avion vole"

def faire_voler(objet):
    print(objet.voler())

oiseau = Oiseau()
avion = Avion()
faire_voler(oiseau)  # Affiche L'oiseau vole
faire_voler(avion)   # Affiche L'avion vole
```

### Conclusion
- Récapitulatif des concepts.
- Importance de la POO dans le développement moderne.
- Questions et réponses.