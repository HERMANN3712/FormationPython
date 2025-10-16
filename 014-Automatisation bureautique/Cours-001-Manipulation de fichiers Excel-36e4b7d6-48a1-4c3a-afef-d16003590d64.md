# Formation : Automatisation Bureautique

## Module 1 : Introduction à l'automatisation bureautique

### Objectifs
- Comprendre les enjeux de l'automatisation dans un environnement bureautique.
- Se familiariser avec les outils et bibliothèques Python pour automatiser les tâches.

### Contenu
- Qu'est-ce que l'automatisation bureautique ?
- Avantages de l'automatisation.
- Présentation des bibliothèques Python : `pandas`, `openpyxl`, `xlrd`, `xlsxwriter`.

---

## Module 2 : Introduction à Excel

### Objectifs
- Comprendre la structure d’un fichier Excel.
- Apprendre à lire et écrire des fichiers Excel en Python.

### Contenu
- Présentation des formats de fichiers Excel (xls, xlsx).
- Vision générale des cellules, lignes, colonnes, et feuilles de calcul.

---

## Module 3 : Manipulation de fichiers Excel avec Pandas

### Objectifs
- Maîtriser la lecture, l'écriture, et la manipulation de fichiers Excel à l'aide de `pandas`.

### Contenu
1. **Installation de pandas**  
   Pour installer `pandas`, exécutez :  
   ```bash
   pip install pandas openpyxl
   ```  

2. **Lecture d'un fichier Excel**  
   ```python
   import pandas as pd  
   df = pd.read_excel('fichier.xlsx')  
   print(df)
   ```  

3. **Écriture d'un fichier Excel**  
   ```python
   df.to_excel('nouveau_fichier.xlsx', index=False)
   ```  

4. **Manipulation des données**  
   - Filtrer des données  
   - Ajouter des colonnes  
   - Supprimer des lignes  

---

## Module 4 : Utilisation d'openpyxl pour la manipulation avancée

### Objectifs
- Explorer des fonctionnalités avancées d'Excel comme la modification de styles et la création de graphiques.

### Contenu
1. **Installation d'openpyxl**  
   ```bash
   pip install openpyxl
   ```  

2. **Lecture d'un fichier Excel**  
   ```python
   from openpyxl import load_workbook  
   wb = load_workbook('fichier.xlsx')  
   sheet = wb.active  
   print(sheet['A1'].value)
   ```  

3. **Modification des styles**  
   ```python
   from openpyxl.styles import Font  
   sheet['A1'].font = Font(bold=True)
   ```  

4. **Création de graphiques**  
   - Utilisation de `Chart` pour créer des graphiques.

---

## Module 5 : Intégration et automatisation

### Objectifs
- Apprendre à intégrer l'utilisation de Excel avec d'autres systèmes et automatiser des processus.

### Contenu
- Créer des scripts Python pour automatiser l'importation et l'exportation de données.
- Planification de l'exécution des scripts avec `cron` ou `Task Scheduler`.

---

## Conclusion

### Résumé
- L'automatisation des manipulations de fichiers Excel permet d'augmenter la productivité et d'éviter les erreurs humaines.

### Prochaines étapes
- Pratiquez avec des projets concrets.
- Explorez d'autres bibliothèques pour des fonctionnalités spéciales (comme `xlwings` pour une interaction avec Excel).  

---