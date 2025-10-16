# TP-001: Sauvegarde Automatique avec Python

## Objectif
L’objectif de ce travail pratique est d’apprendre à automatiser la sauvegarde de fichiers à l’aide de Python. Les étudiants découvriront comment créer un script simple qui copiera des fichiers d’un répertoire source vers un répertoire de destination, tout en appliquant quelques principes de gestion d’erreurs.

## Prérequis
- Python 3 installé sur votre machine.
- Connaissances de base en Python.
- Un environnement de développement (par exemple, un éditeur de code ou un IDE).

## Matériel nécessaire
- Un dossier `source` contenant des fichiers à sauvegarder.
- Un dossier `destination` où les fichiers seront sauvegardés.

## Instructions
1. **Création des répertoires**
   - Créez deux dossier : `source` et `destination` dans votre répertoire de travail.
2. **Création du script**
   - Ouvrez votre éditeur de code et créez un fichier nommé `sauvegarde.py`.
3. **Écrire le code**
   - Dans `sauvegarde.py`, écrivez le code suivant :
     ```python
     import os
     import shutil
     from datetime import datetime
     
     def sauvegarder(source, destination):
         try:
             # Vérifie si le dossier source existe
             if not os.path.exists(source):
                 raise FileNotFoundError(f"Le dossier source '{source}' n'existe pas.")
             
             # Crée le dossier destination s'il n'existe pas
             if not os.path.exists(destination):
                 os.makedirs(destination)
             
             # Copie les fichiers
             for fichier in os.listdir(source):
                 chemin_source = os.path.join(source, fichier)
                 chemin_destination = os.path.join(destination, fichier)
                 shutil.copy2(chemin_source, chemin_destination)
                 print(f"'{fichier}' a été sauvegardé avec succès.")
         except Exception as e:
             print(f"Erreur: {str(e)}")
     
     if __name__ == "__main__":
         source_dir = 'source'
         destination_dir = os.path.join('destination', datetime.now().strftime('%Y%m%d_%H%M%S'))
         sauvegarder(source_dir, destination_dir)
     ```
4. **Exécution du script**
   - Exécutez le script via votre terminal ou IDE : `python sauvegarde.py`
5. **Vérification**
   - Vérifiez le contenu du dossier `destination` pour vous assurer que les fichiers ont été copiés.

## Corrigé
Voici quelques points clés à vérifier pour le corrigé :
- Le script doit vérifier l'existence du dossier source.
- Les fichiers doivent être copiés dans le dossier de destination avec un horodatage.
- Toutes les exceptions doivent être gérées avec des messages d'erreur appropriés.
- L'utilisateur doit être informé de la réussite ou de l'échec de la sauvegarde.

## Conclusion
Cet exercice a permis de comprendre comment utiliser Python pour automatiser la sauvegarde de fichiers, une compétence essentielle pour l'administration système.