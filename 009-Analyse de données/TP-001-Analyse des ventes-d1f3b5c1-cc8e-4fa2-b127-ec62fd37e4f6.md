# TP-001 : Analyse des ventes

## Objectif
L'objectif de ce travail pratique est de manipuler et de visualiser des données de ventes à l'aide de la bibliothèque Pandas et de créer des visualisations avec Matplotlib.

## Description du projet
Dans ce TP, vous allez travailler avec un jeu de données fictif qui contient des informations sur les ventes d'un magasin. Vous apprendrez à effectuer des manipulations de données, des analyses statistiques et à créer des graphiques.

### Données
Le jeu de données contient les colonnes suivantes :
- `Date` : La date de la vente
- `Produit` : Le nom du produit vendu
- `Quantité` : Le nombre d'unités vendues
- `Prix_Unitaire` : Le prix unitaire du produit
- `Total_Vente` : Montant total de la vente (Quantité x Prix Unitaire)

Le fichier CSV peut être téléchargé ici : [Ventes.csv](#)

## Instructions
1. **Chargement des données**
   - Utilisez Pandas pour charger le fichier CSV.
   - Affichez les 5 premières lignes du dataset.

2. **Manipulation des données**
   - Calculez le chiffre d'affaires total du magasin.
   - Quel produit a généré le plus de ventes ?

3. **Visualisation des données**
   - Créez un graphique à barres pour montrer le total des ventes par produit.
   - Créez un graphique linéaire montrant l'évolution des ventes au fil du temps.

### Exemples de code
Voici quelques exemples de code pour vous aider :

#### Chargement des données
```python
import pandas as pd

df = pd.read_csv('Ventes.csv')
print(df.head())
```

#### Calcul du chiffre d'affaires total
```python
chiffre_affaires_total = df['Total_Vente'].sum()
print(f'Chiffre d affaires total: {chiffre_affaires_total}')
```

#### Visualisation
```python
import matplotlib.pyplot as plt

# Total des ventes par produit
ventes_par_produit = df.groupby('Produit')['Total_Vente'].sum()
ventes_par_produit.plot(kind='bar')
plt.title('Total des ventes par produit')
plt.xlabel('Produit')
plt.ylabel('Total des ventes')
plt.show()

# Évolution des ventes au fil du temps
ventes_par_date = df.groupby('Date')['Total_Vente'].sum()
ventes_par_date.plot(kind='line')
plt.title('Évolution des ventes au fil du temps')
plt.xlabel('Date')
plt.ylabel('Total des ventes')
plt.show()
```

## Corrigé
### 1. Chargement des données
```python
import pandas as pd

df = pd.read_csv('Ventes.csv')
print(df.head())
```
### 2. Manipulation des données
```python
chiffre_affaires_total = df['Total_Vente'].sum()
produit_max_ventes = df.groupby('Produit')['Total_Vente'].sum().idxmax()
print(f'Chiffre d affaires total: {chiffre_affaires_total}')
print(f'Produit le plus vendu: {produit_max_ventes}')
```
### 3. Visualisation
```python
import matplotlib.pyplot as plt

# Total des ventes par produit
ventes_par_produit = df.groupby('Produit')['Total_Vente'].sum()
ventes_par_produit.plot(kind='bar')
plt.title('Total des ventes par produit')
plt.xlabel('Produit')
plt.ylabel('Total des ventes')
plt.show()

# Évolution des ventes au fil du temps
ventes_par_date = df.groupby('Date')['Total_Vente'].sum()
ventes_par_date.plot(kind='line')
plt.title('Évolution des ventes au fil du temps')
plt.xlabel('Date')
plt.ylabel('Total des ventes')
plt.show()
```

## Conclusion
Ce TP vous a permis de découvrir l'analyse de données avec Pandas et la visualisation avec Matplotlib. Vous pouvez approfondir vos connaissances en explorant d'autres fonctionnalités de ces bibliothèques.