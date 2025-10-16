# Travail Pratique : Prédiction de Prix Immobiliers avec Scikit-learn

## Objectif
L'objectif de ce travail pratique est de découvrir l'entraînement de modèles prédictifs à l'aide de la bibliothèque Scikit-learn en Python. Vous apprendrez à manipuler des données, à créer un modèle de prédiction, et à évaluer sa performance.

## Pré-requis
- Avoir Python installé (version 3.6 ou supérieure)
- Installer les bibliothèques nécessaires :
  - `pandas`
  - `numpy`
  - `scikit-learn`
  - `matplotlib`

Pour installer ces bibliothèques, vous pouvez utiliser pip :
```bash
pip install pandas numpy scikit-learn matplotlib
```

## Description du Dataset
Nous allons utiliser un jeu de données fictif sur les prix immobiliers. Le jeu de données comprend les colonnes suivantes :
- `Surface` : Surface en mètres carrés
- `Chambres` : Nombre de chambres
- `Salle_de_bain` : Nombre de salles de bain
- `Prix` : Prix en euros

## Étape 1 : Chargement des Données
Créez un fichier Python nommé `prix_immo.py` et commencez par charger les données.
```python
import pandas as pd

# Charger le dataset
df = pd.read_csv('prix_immo.csv')
print(df.head())
```

## Étape 2 : Préparation des Données
- Vérifiez les valeurs manquantes et retirez/complétez-les si nécessaire.
- Séparez les variables dépendantes (Prix) et indépendantes (Surface, Chambres, Salle_de_bain).
```python
# Vérification des valeurs manquantes
df.isnull().sum()

# Préparation des données
y = df['Prix']
X = df[['Surface', 'Chambres', 'Salle_de_bain']]
```

## Étape 3 : Division du Dataset
Divisez le dataset en un ensemble d'entraînement et un ensemble de test.
```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

## Étape 4 : Création du Modèle
Utilisez un modèle de régression linéaire.
```python
from sklearn.linear_model import LinearRegression

# Création du modèle
model = LinearRegression()
model.fit(X_train, y_train)
```

## Étape 5 : Prédiction
Faites des prédictions sur l'ensemble de test.
```python
# Prédictions
y_pred = model.predict(X_test)
```

## Étape 6 : Évaluation du Modèle
Évaluez la performance de votre modèle à l'aide de l'erreur quadratique moyenne (RMSE).
```python
from sklearn.metrics import mean_squared_error
import numpy as np

# Évaluation
rmse = np.sqrt(mean_squared_error(y_test, y_pred))
print(f'Erreur Quadratique Moyenne : {rmse}')
```

## Étape 7 : Visualisation des Résultats
Visualisez les résultats pour mieux comprendre la performance du modèle.
```python
import matplotlib.pyplot as plt

plt.scatter(y_test, y_pred)
plt.xlabel('Prix Réels')
plt.ylabel('Prix Prédits')
plt.title('Comparaison des Prix Réels et Prédits')
plt.show()
```

## Corrigé du TP
Voici le code complet pour le travail pratique :
```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error
import numpy as np
import matplotlib.pyplot as plt

# Charger le dataset
df = pd.read_csv('prix_immo.csv')

# Vérification des valeurs manquantes
df.isnull().sum()

# Préparation des données
y = df['Prix']
X = df[['Surface', 'Chambres', 'Salle_de_bain']]

# Division du dataset
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Création du modèle
model = LinearRegression()
model.fit(X_train, y_train)

# Prédictions
y_pred = model.predict(X_test)

# Évaluation
rmse = np.sqrt(mean_squared_error(y_test, y_pred))
print(f'Erreur Quadratique Moyenne : {rmse}')

# Visualisation des résultats
plt.scatter(y_test, y_pred)
plt.xlabel('Prix Réels')
plt.ylabel('Prix Prédits')
plt.title('Comparaison des Prix Réels et Prédits')
plt.show()
```

## Conclusion
Ce travail pratique vous a permis de découvrir les étapes de création d'un modèle de prédiction des prix immobiliers avec Scikit-learn. Vous avez appris à charger des données, à les préparer, à entraîner un modèle, et à évaluer sa performance.