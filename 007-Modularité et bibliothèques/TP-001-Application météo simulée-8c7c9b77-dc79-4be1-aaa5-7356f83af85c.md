# Application Météo Simulée

## Objectif
Ce travail pratique a pour objectif de créer une application météo simple en Python qui utilise des modules et des bibliothèques. Au terme de cette formation, les participants devraient être capables de structurer un projet Python en utilisant des modules et de faire appel à des bibliothèques pour enrichir leurs fonctionnalités.

## Contexte
L'application météo simulée affichera la température, les conditions météorologiques et un message personnalisé en fonction de la météo pour une ville donnée. Les participants apprendront à:
- Créer des modules Python.
- Utiliser des bibliothèques externes comme `requests` pour simuler des requêtes d'API.

## Structure du Projet
Voici comment structurer le projet:
```
mois
|-- app/
|    |-- __init__.py
|    |-- weather.py
|-- main.py
|-- requirements.txt
```

### Fichiers
1. **`__init__.py`** : Ce fichier peut être vide, il indique que le répertoire `app` doit être traité comme un package Python.
2. **`weather.py`** : Contient la logique de l'application météo.
3. **`main.py`** : Point d'entrée de l'application.
4. **`requirements.txt`** : Liste des bibliothèques nécessaires (ex: requests).

## Étapes
### 1. Créer le fichier `weather.py`
Ce fichier contiendra une fonction pour obtenir un rapport météo simulé.
```python
import random

def get_weather(city):
    conditions = ['Ensoleillé', 'Nuageux', 'Pluvieux']
    temp = random.randint(-10, 35)  # température entre -10 et 35
    condition = random.choice(conditions)
    return f'Dans {city}, il fait {temp}°C et c'est {condition}.'
```

### 2. Créer le fichier `main.py`
Ce fichier importera le module et exécutera l'application.
```python
from app.weather import get_weather

def main():
    city = input('Entrez le nom de la ville: ')
    weather_report = get_weather(city)
    print(weather_report)

if __name__ == '__main__':
    main()
```

### 3. Créer le fichier `requirements.txt`
Ajoutez la bibliothèque suivante :
```
requests
```

### 4. Exécuter l'application
1. Installez les bibliothèques à l'aide de pip:
```bash
pip install -r requirements.txt
```
2. Lancez l'application:
```bash
python main.py
``` 

## Corrigé
- Lorsque l'utilisateur lance `main.py`, il sera invité à entrer le nom d'une ville.
- Le programme affichera un rapport météo simulé qui indique la température et l'état du temps (ensoleillé, nuageux, pluvieux).

### Exemple d'Entrée/Sortie:
```
Entrez le nom de la ville: Paris
Dans Paris, il fait 22°C et c'est Ensoleillé.
```

## Conclusion
Cette application simple permet de comprendre comment structurer un projet Python en utilisant des modules et de s'initier à l'utilisation de bibliothèques externes. Les participants peuvent étendre cette application en ajoutant des fonctionnalités supplémentaires comme la récupération de données d'une vraie API météo.