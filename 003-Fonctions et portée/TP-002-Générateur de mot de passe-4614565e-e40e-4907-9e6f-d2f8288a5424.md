# Travail Pratique : Générateur de Mot de Passe

## Objectif
Ce travail pratique vise à vous familiariser avec la création de fonctions en Python et à vous permettre d'organiser votre code de manière efficace. Vous allez développer un générateur de mot de passe qui prendra en compte différents critères.

## Instructions

### 1. Création des Fonctions

Vous devrez créer les fonctions suivantes :

- **`generer_mot_de_passe(longueur, utiliser_chiffres=True, utiliser_special=True)`** : Cette fonction génère un mot de passe aléatoire basé sur les paramètres fournis.
  - `longueur` : La longueur du mot de passe souhaité.
  - `utiliser_chiffres` : Indique si des chiffres doivent être inclus (par défaut `True`).
  - `utiliser_special` : Indique si des caractères spéciaux doivent être inclus (par défaut `True`).

- **`mot_de_passe_valide(mot_de_passe)`** : Vérifie si le mot de passe généré respecte certaines règles (longueur minimale, inclusion de chiffres, inclusion de caractères spéciaux).

### 2. Exemple de Fonctionnalité

Voici un exemple d'utilisation de vos fonctions :

```python
if __name__ == '__main__':
    longueur = int(input("Entrez la longueur du mot de passe: "))
    mot_de_passe = generer_mot_de_passe(longueur)
    print(f"Mot de passe généré : {mot_de_passe}")
```

### 3. Critères de Réussite
- Le programme doit générer des mots de passe qui répondent aux critères suivants :
  - Longueur minimale de 8 caractères.
  - Inclusion d'au moins un chiffre si `utiliser_chiffres` est `True`.
  - Inclusion d'au moins un caractère spécial si `utiliser_special` est `True`.

## Corrigé

### 1. Implémentation des Fonctions

```python
import random
import string


def generer_mot_de_passe(longueur, utiliser_chiffres=True, utiliser_special=True):
    caracteres = string.ascii_letters  # Lettres (majuscules et minuscules)
    if utiliser_chiffres:
        caracteres += string.digits  # Ajout des chiffres
    if utiliser_special:
        caracteres += string.punctuation  # Ajout des caractères spéciaux

    mot_de_passe = ''.join(random.choice(caracteres) for _ in range(longueur))
    return mot_de_passe


def mot_de_passe_valide(mot_de_passe):
    if len(mot_de_passe) < 8:
        return False
    if not any(c.isdigit() for c in mot_de_passe):
        return False
    if not any(c in string.punctuation for c in mot_de_passe):
        return False
    return True


if __name__ == '__main__':
    longueur = int(input("Entrez la longueur du mot de passe: "))
    mot_de_passe = generer_mot_de_passe(longueur)
    while not mot_de_passe_valide(mot_de_passe):
        mot_de_passe = generer_mot_de_passe(longueur)
    print(f"Mot de passe généré : {mot_de_passe}")
```

### 2. Explications
- La fonction `generer_mot_de_passe` construit un mot de passe en choisissant aléatoirement des caractères dans la liste prédéfinie.
- La fonction `mot_de_passe_valide` vérifie que le mot de passe respecte les critères de sécurité.

### 3. Tests Unitaires
Vous pouvez également écrire des tests unitaires pour vérifier que vos fonctions fonctionnent comme prévu.

```python
import unittest

class TestMotDePasse(unittest.TestCase):

    def test_generation_mot_de_passe(self):
        mot_de_passe = generer_mot_de_passe(12)
        self.assertEqual(len(mot_de_passe), 12)
        self.assertTrue(mot_de_passe_valide(mot_de_passe))

if __name__ == '__main__':
    unittest.main()
```

### 4. Conclusion
Ce travail pratique vous a permis de manipuler des fonctions et d'organiser votre code en Python. N'hésitez pas à modifier le générateur pour l'adapter à vos besoins!