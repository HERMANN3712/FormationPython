# Travail Pratique : Visualisation Météo avec Python

## Objectifs

L'objectif de ce travail pratique est de vous familiariser avec la manipulation et la visualisation de données météorologiques. Vous utiliserez les bibliothèques `pandas` pour le traitement des données et `matplotlib` pour la visualisation.

## Pré-requis

- Avoir installé les bibliothèques `pandas` et `matplotlib` :
  ```bash
  pip install pandas matplotlib
  ```

## Données

Pour ce TP, nous allons utiliser un fichier CSV contenant des données météorologiques. Le fichier contient les colonnes suivantes :
- `Date` : date de l'observation
- `Température (°C)` : température maximale de la journée
- `Précipitations (mm)` : précipitations de la journée

### Exemple de Données

| Date       | Température (°C) | Précipitations (mm) |
|------------|------------------|---------------------|
| 2022-01-01 | 5                | 0                   |
| 2022-01-02 | 7                | 1                   |
| 2022-01-03 | 6                | 0                   |
| 2022-01-04 | 4                | 5                   |

## Instructions

1. **Chargement des Données**  
   Utilisez `pandas` pour lire le fichier CSV contenant les données météorologiques dans un DataFrame.
   ```python
   import pandas as pd
   df = pd.read_csv('meteo.csv')
   ```

2. **Exploration des Données**  
   Affichez les 5 premières lignes de votre DataFrame pour vous assurer que les données sont correctement chargées.
   ```python
   print(df.head())
   ```

3. **Visualisation des Températures**  
   Créez un graphique linéaire montrant l'évolution de la température au fil du temps.
   ```python
   import matplotlib.pyplot as plt
   
   plt.figure(figsize=(10, 5))
   plt.plot(df['Date'], df['Température (°C)'], marker='o')
   plt.title('Évolution de la Température')
   plt.xlabel('Date')
   plt.ylabel('Température (°C)')
   plt.xticks(rotation=45)
   plt.grid()
   plt.show()
   ```

4. **Visualisation des Précipitations**  
   Créez un histogramme des précipitations pour visualiser la répartition des jours avec et sans pluie.
   ```python
   plt.figure(figsize=(10, 5))
   plt.hist(df['Précipitations (mm)'], bins=10, alpha=0.7)
   plt.title('Répartition des Précipitations')
   plt.xlabel('Précipitations (mm)')
   plt.ylabel('Nombre de Jours')
   plt.grid()
   plt.show()
   ```

## Corrigé

### Chargement des Données
```python
import pandas as pd

df = pd.read_csv('meteo.csv')
print(df.head())
```

### Création des Graphiques

**Évolution de la Température**  
```python
import matplotlib.pyplot as plt

plt.figure(figsize=(10, 5))
plt.plot(df['Date'], df['Température (°C)'], marker='o')
plt.title('Évolution de la Température')
plt.xlabel('Date')
plt.ylabel('Température (°C)')
plt.xticks(rotation=45)
plt.grid()
plt.show()
```

**Histograms des Précipitations**  
```python
plt.figure(figsize=(10, 5))
plt.hist(df['Précipitations (mm)'], bins=10, alpha=0.7)
plt.title('Répartition des Précipitations')
plt.xlabel('Précipitations (mm)')
plt.ylabel('Nombre de Jours')
plt.grid()
plt.show()
```

## Conclusion

Dans ce travail pratique, vous avez appris à manipuler et visualiser des données météorologiques avec `pandas` et `matplotlib`. Vous pouvez maintenant explorer d'autres ensembles de données et créer des visualisations en fonction de vos besoins.