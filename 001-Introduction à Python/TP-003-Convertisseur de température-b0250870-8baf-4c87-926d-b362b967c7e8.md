# TP-003 : Convertisseur de Température

## Objectif
L'objectif de ce travail pratique est de créer un convertisseur de température qui permettra de convertir des températures entre Celsius et Fahrenheit.

## Pré-requis
- Connaître les bases de la syntaxe Python.
- Avoir un environnement Python installé (Python 3.x).

## Instructions

### Étape 1 : Création du Script
1. Ouvrez votre éditeur de texte ou votre IDE préféré.
2. Créez un nouveau fichier appelé `convertisseur_temperature.py`.

### Étape 2 : Écrire le Code
Dans le fichier que vous venez de créer, écrivez le code suivant :

```python
# Fonction de conversion Celsius vers Fahrenheit
def celsius_vers_fahrenheit(celsius):
    return (celsius * 9/5) + 32

# Fonction de conversion Fahrenheit vers Celsius
def fahrenheit_vers_celsius(fahrenheit):
    return (fahrenheit - 32) * 5/9

# Demander à l'utilisateur de choisir la conversion
print("Choisissez la conversion :")
print("1 : Celsius vers Fahrenheit")
print("2 : Fahrenheit vers Celsius")
choix = input("Entrez votre choix (1 ou 2) : ")

if choix == '1':
    celsius = float(input("Entrez la température en Celsius : "))
    print(f"{celsius}°C équivaut à {celsius_vers_fahrenheit(celsius):.2f}°F")
elif choix == '2':
    fahrenheit = float(input("Entrez la température en Fahrenheit : "))
    print(f"{fahrenheit}°F équivaut à {fahrenheit_vers_celsius(fahrenheit):.2f}°C")
else:
    print("Choix invalide, veuillez essayer à nouveau.")
```

### Étape 3 : Tester le Script
1. Enregistrez le fichier.
2. Exécutez le script depuis votre terminal :  
   ```bash
   python convertisseur_temperature.py
   ```
3. Suivez les instructions affichées pour effectuer des conversions.

## Correction
Voici ce que devrait produire le script :

- Si l'utilisateur entre `25` pour Celsius, la sortie devrait être :  
  `25°C équivaut à 77.00°F`  
- Si l'utilisateur entre `77` pour Fahrenheit, la sortie devrait être :  
  `77°F équivaut à 25.00°C`

## Conclusion
Félicitations, vous avez créé votre premier convertisseur de température en Python!  
Ce projet permet de comprendre les bases de la gestion des entrées et sorties utilisateurs, ainsi que l'utilisation de fonctions en Python.