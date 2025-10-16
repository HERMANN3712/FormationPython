# Travail Pratique : Système de Comptes Bancaires

## Objectif
L'objectif de ce travail pratique est d'apprendre à structurer le code en Python en utilisant la programmation orientée objet. Vous allez créer un système de gestion de comptes bancaires avec des classes et des objets.

## Instructions
1. Créez une classe `CompteBancaire` avec les attributs suivants :  
   - `titulaire` (le nom du titulaire du compte)  
   - `solde` (le solde du compte, initialisé à 0)  

2. Implémentez les méthodes suivantes :  
   - `deposer(montant)`: permet de déposer de l'argent sur le compte. Le montant doit être positif.  
   - `retirer(montant)`: permet de retirer de l'argent du compte. Le montant doit être positif et ne doit pas dépasser le solde du compte.  
   - `afficher_solde()`: affiche le solde actuel du compte.  

3. Créez une classe `Banque` qui gère plusieurs comptes bancaires. Cette classe doit avoir les méthodes suivantes :  
   - `ajouter_compte(compte)`: ajoute un nouvel objet `CompteBancaire` à la liste des comptes de la banque.  
   - `afficher_comptes()`: affiche les informations de tous les comptes de la banque.  

## Exemple d'implémentation
Voici un petit exemple d'implémentation pour vous aider à démarrer :

```python
class CompteBancaire:
    def __init__(self, titulaire):
        self.titulaire = titulaire
        self.solde = 0

    def deposer(self, montant):
        if montant > 0:
            self.solde += montant
            print(f"{montant} a été déposé. Nouveau solde: {self.solde}")
        else:
            print("Le montant doit être positif.")

    def retirer(self, montant):
        if 0 < montant <= self.solde:
            self.solde -= montant
            print(f"{montant} a été retiré. Nouveau solde: {self.solde}")
        else:
            print("Fonds insuffisants ou montant invalide.")

    def afficher_solde(self):
        print(f"Solde actuel de {self.titulaire}: {self.solde}")


class Banque:
    def __init__(self):
        self.comptes = []

    def ajouter_compte(self, compte):
        self.comptes.append(compte)

    def afficher_comptes(self):
        for compte in self.comptes:
            compte.afficher_solde()
```

## Correction
1. **Classe CompteBancaire**:  
   - Vérifiez que les méthodes `deposer` et `retirer` gèrent correctement les entrées.  
   - Vérifiez que `afficher_solde` affiche le bon solde.

2. **Classe Banque**:  
   - Assurez-vous que `ajouter_compte` fonctionne et ajoute les comptes correctement.  
   - Vérifiez que `afficher_comptes` affiche tous les comptes et leurs soldes.

## Conclusion
Ce travail pratique vous a permis d'apprendre à structurer votre code en utilisant la programmation orientée objet. Vous avez créé une application simple mais fonctionnelle de gestion de comptes bancaires avec des classes et des objets.