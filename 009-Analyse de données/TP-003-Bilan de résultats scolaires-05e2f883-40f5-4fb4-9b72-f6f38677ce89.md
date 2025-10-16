# Travail Pratique : Bilan de résultats scolaires

## Objectifs
* Apprendre à manipuler des données avec **Pandas**.
* Visualiser des données à l'aide de **Matplotlib**.

## Contexte
Dans ce travail pratique, vous serez amené à analyser un jeu de données représentant les résultats scolaires d'étudiants dans différentes matières. Vous allez effectuer des opérations de nettoyage, de transformation et de visualisation des données.

## Jeu de données
Le jeu de données contient les colonnes suivantes :
- `Nom` : Le nom de l'étudiant
- `Maths` : Résultat en mathématiques (sur 20)
- `Physique` : Résultat en physique (sur 20)
- `Chimie` : Résultat en chimie (sur 20)
- `Biologie` : Résultat en biologie (sur 20)

Voici un extrait des données :

| Nom       | Maths | Physique | Chimie | Biologie |
|-----------|-------|----------|--------|----------|
| Alice     | 15    | 14       | 16     | 18       |
| Bob       | 12    | 16       | 11     | 15       |
| Charlie   | 10    | 10       | 14     | 17       |

## Exercice 1 : Chargement et exploration des données
1. Importez les librairies nécessaires :
   ```python
   import pandas as pd
   import matplotlib.pyplot as plt
   ```
2. Chargez le fichier CSV contenant les résultats scolaires :
   ```python
   df = pd.read_csv('resultats_scolaires.csv')
   ```
3. Affichez les premières lignes du dataframe :
   ```python
   print(df.head())
   ```

## Exercice 2 : Nettoyage des données
1. Vérifiez s'il y a des valeurs manquantes dans le dataframe :
   ```python
   print(df.isnull().sum())
   ```
2. Si des valeurs manquantes sont présentes, gérez-les avec une méthode appropriée (suppression ou imputation).

## Exercice 3 : Analyse des résultats
1. Calculez la moyenne des résultats pour chaque matière :
   ```python
   moyennes = df.mean()
   print(moyennes)
   ```
2. Créez un graphique barres pour visualiser les moyennes des résultats :
   ```python
   moyennes.plot(kind='bar')
   plt.title('Moyenne des résultats par matière')
   plt.xlabel('Matières')
   plt.ylabel('Moyenne')
   plt.show()
   ```

## Exercice 4 : Visualisation des résultats individuels
1. Créez un graphique en boîte pour visualiser la distribution des résultats pour chaque matière :
   ```python
   df.boxplot()
   plt.title('Distribution des résultats')
   plt.ylabel('Scores')
   plt.show()
   ```

## Corrigé
### Exercice 1 : Chargement et exploration des données
```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv('resultats_scolaires.csv')
print(df.head())
```
### Exercice 2 : Nettoyage des données
```python
print(df.isnull().sum())
# Gérer les valeurs manquantes selon le besoin
```
### Exercice 3 : Analyse des résultats
```python
moyennes = df.mean()
print(moyennes)
moyennes.plot(kind='bar')
plt.title('Moyenne des résultats par matière')
plt.xlabel('Matières')
plt.ylabel('Moyenne')
plt.show()
```
### Exercice 4 : Visualisation des résultats individuels
```python
df.boxplot()
plt.title('Distribution des résultats')
plt.ylabel('Scores')
plt.show()
```