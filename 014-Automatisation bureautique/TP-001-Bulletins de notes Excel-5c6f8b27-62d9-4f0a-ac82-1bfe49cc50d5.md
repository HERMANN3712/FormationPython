# Travail Pratique : Bulletins de Notes Excel

## Objectif
L'objectif de ce travail pratique est de créer un fichier Excel générant des bulletins de notes pour des étudiants. Vous apprendrez à automatiser la création de fichiers Excel et à mettre en forme les données de manière appropriée.

## Prérequis
- Python installé (version 3.x)
- Bibliothèque `openpyxl` installée. Vous pouvez l'installer avec la commande suivante :  
  `pip install openpyxl`

## Étapes à Suivre

### 1. Créer le fichier Python
Créez un fichier nommé `bulletin_notes.py`.

### 2. Importer les bibliothèques nécessaires
Dans votre fichier `bulletin_notes.py`, commencez par importer la bibliothèque `openpyxl` :

```python
import openpyxl
from openpyxl.styles import Font, PatternFill
```

### 3. Créer un nouveau classeur Excel
Ajoutez le code suivant pour créer un nouveau classeur et une nouvelle feuille de calcul :

```python
# Créer un classeur
classeur = openpyxl.Workbook()
feuille = classeur.active
feuille.title = 'Bulletin des Notes'
```

### 4. Ajouter les en-têtes des colonnes
Ajoutez le code suivant pour déclarer et styliser les en-têtes :

```python
# Définir les en-têtes des colonnes
entetes = ['Nom', 'Prénom', 'Mathématiques', 'Sciences', 'Histoire', 'Moyenne']
for col_num, header in enumerate(entetes, 1):
    cellule = feuille.cell(row=1, column=col_num)
    cellule.value = header
    cellule.font = Font(bold=True)
    cellule.fill = PatternFill(start_color='00FFCC', end_color='00FFCC', fill_type='solid')
```

### 5. Ajouter des données d'exemple
Ajoutez le code suivant pour entrer des données d'étudiants :

```python
# Données des étudiants
etudiants = [
    {'nom': 'Dupont', 'prenom': 'Jean', 'math': 15, 'sciences': 14, 'histoire': 12},
    {'nom': 'Martin', 'prenom': 'Sophie', 'math': 18, 'sciences': 16, 'histoire': 15},
]

# Remplir les données dans le fichier
for row_num, etudiant in enumerate(etudiants, 2):
    feuille.cell(row=row_num, column=1).value = etudiant['nom']
    feuille.cell(row=row_num, column=2).value = etudiant['prenom']
    feuille.cell(row=row_num, column=3).value = etudiant['math']
    feuille.cell(row=row_num, column=4).value = etudiant['sciences']
    feuille.cell(row=row_num, column=5).value = etudiant['histoire']
    moyenne = (etudiant['math'] + etudiant['sciences'] + etudiant['histoire']) / 3
    feuille.cell(row=row_num, column=6).value = moyenne
```

### 6. Enregistrer le fichier
Ajoutez le code suivant pour enregistrer le fichier Excel avec un nom :

```python
# Enregistrer le fichier
classeur.save('bulletins_de_notes.xlsx')
```

### 7. Lancer le script
En ligne de commande, exécutez le script Python :
```bash
python bulletin_notes.py
```

## Corrigé
Le travail pratique sera considéré comme réussi si le script Python s'exécute sans erreur et génère le fichier `bulletins_de_notes.xlsx` avec la mise en forme correcte et les données pour les étudiants ajoutés.

## Conclusion
Dans ce travail pratique, vous avez appris à créer un fichier Excel contenant des bulletins de notes pour des étudiants, à styliser les en-têtes, et à calculer la moyenne des notes. Cela constitue un bon exemple d'automatisation bureautique avec Python.