# Rapport de TP - Hello World interactif

## Objectif
L'objectif de ce travail pratique est de créer un programme Python qui affiche "Hello, World!" de manière interactive et visuellement attrayante.

## Prérequis
- Avoir Python installé sur votre machine (version 3.6 ou supérieure).
- Connaître les bases de la ligne de commande.

## Étapes

### 1. Création de l'environnement de travail
- Créez un dossier sur votre bureau nommé `formation_python`.
- À l'intérieur, créez un sous-dossier nommé `TP-001-Hello_World`.

### 2. Écriture du script Python
- Ouvrez un éditeur de texte (comme VSCode, PyCharm, ou même un simple Notepad).
- Créez un nouveau fichier appelé `hello.py` dans le dossier `TP-001-Hello_World`.

### 3. Code du script
Ajoutez le code suivant dans le fichier `hello.py` :

```python
# hello.py

def main():
    name = input("Entrez votre nom: ")  # Demande d'entrée à l'utilisateur
    print(f"Hello, {name}! Bienvenue dans l'univers de Python!")

if __name__ == "__main__":
    main()
```

### 4. Exécution du script
- Ouvrez votre terminal.
- Naviguez jusqu'au dossier où se trouve votre fichier `hello.py`.
- Exécutez le script en tapant la commande suivante :
  ```bash
  python hello.py
  ```

### 5. Résultat attendu
- Le programme demandera à l'utilisateur d'entrer son nom.
- Une fois le nom renseigné, il affichera un message de bienvenue personnalisé.

### 6. Questions de réflexion
- Modifiez le script pour qu'il demande une autre entrée, comme l'âge de l'utilisateur, et l'affiche également.
- Que se passe-t-il si l'utilisateur n'entre rien ? Comment pouvez-vous gérer cette situation ?

## Corrigé
Voici un exemple de ce à quoi devrait ressembler l'exécution du script :
```
Entrez votre nom: Alice
Hello, Alice! Bienvenue dans l'univers de Python!
```

N'hésitez pas à modifier et améliorer le script pour explorer davantage les fonctionnalités de Python. Ce travail pratique vous permet de vous familiariser avec les entrées utilisateur et l'affichage dynamique en Python.