# TP-002: Fusion de Rapports Word

## Objectif
Apprendre à fusionner des documents Word de manière automatisée en utilisant Python et la bibliothèque `python-docx`. Ce TP vous guidera dans la création d'un script qui combinera plusieurs rapports Word en un seul document final.

## Pré-requis
- Connaissance de base en Python.
- Installation des bibliothèques nécessaires : `python-docx`.

## Méthodologie
1. **Installation des bibliothèques** :
   Assurez-vous que la bibliothèque `python-docx` est installée. Vous pouvez l'installer via pip :
   ```bash
   pip install python-docx
   ```

2. **Création des documents Word à fusionner** :
   Créez quelques documents Word simples que vous souhaitez fusionner. Par exemple:
   - `rapport1.docx`
   - `rapport2.docx`
   - `rapport3.docx`

   Ajoutez quelques textes et éléments graphiques pour rendre les rapports intéressants.

3. **Écriture du script de fusion** :
   Créez un script Python `fusionner_rapports.py`. 

   ```python
   from docx import Document
   import os

   def fusionner_documents(chemin_documents):
       document_final = Document()
       for chemin in chemin_documents:
           doc = Document(chemin)
           for element in doc.element.body:
               document_final.element.body.append(element)
       document_final.save('rapport_fusionne.docx')

   # Chemins des documents à fusionner
   chemins = ['rapport1.docx', 'rapport2.docx', 'rapport3.docx']
   fusionner_documents(chemins)
   ```

4. **Exécution du script** :
   Dans votre terminal, exécutez le script :
   ```bash
   python fusionner_rapports.py
   ```

   Cela créera un fichier `rapport_fusionne.docx` contenant le contenu de tous les documents.

5. **Vérification du résultat** :
   Ouvrez `rapport_fusionne.docx` pour vérifier que tous les rapports ont été fusionnés correctement.

## Corrigé
Le script Python ci-dessus fusionne plusieurs documents Word en un seul. Voici les étapes à suivre (en réponse aux étapes de méthodologie):
- La méthode `fusionner_documents` prend une liste de chemins de fichiers comme argument.
- Pour chaque document, il lit le contenu et l'ajoute au document final.
- Finalement, le document fusionné est enregistré sous le nom `rapport_fusionne.docx`.

## Conclusion
Grâce à ce TP, vous avez appris à automatiser la fusion de documents Word avec Python. Cette technique peut être utilisée dans divers domaines où la génération de rapports est nécessaire.