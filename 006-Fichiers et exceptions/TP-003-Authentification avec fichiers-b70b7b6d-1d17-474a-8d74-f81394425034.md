# Travail Pratique : Authentification avec fichiers

## Objectif
L'objectif de ce travail pratique est de mettre en œuvre un système simple d'authentification à l'aide de fichiers en Python. Ce TP vous permettra de lire et d'écrire des fichiers tout en gérant les exceptions potentielles.

## Pré-requis
Avoir des notions de base en Python, ainsi que des connaissances sur la gestion des fichiers et des exceptions.

## Description
Dans ce travail pratique, vous allez créer un système d'authentification qui permet aux utilisateurs de se connecter. Les informations d'identification (noms d'utilisateur et mots de passe) seront stockées dans un fichier.

## Étapes à réaliser

### 1. Création du fichier avec les identifiants
- Créez un fichier `credentials.txt` dans lequel vous allez stocker les informations d'identification sous le format : `username:password`

### 2. Écriture de la fonction d'inscription
- Écrivez une fonction `register(username, password)` qui ajoute un nouvel utilisateur au fichier `credentials.txt`.
- Assurez-vous de gérer les exceptions si l'utilisateur tente de s'inscrire avec un nom d'utilisateur déjà existant.

### 3. Écriture de la fonction de connexion
- Écrivez une fonction `login(username, password)` qui vérifie si l'utilisateur et le mot de passe fournis correspondent à une entrée dans `credentials.txt`.
- Gérer les cas d'erreur si l'utilisateur n'existe pas ou si le mot de passe est incorrect.

### 4. Tester le programme
- Dans le `main`, testez l'inscription et la connexion avec différents utilisateurs. Assurez-vous de gérer les exceptions correctement et d'en informer l'utilisateur.

## Exemple de code
Voici un exemple de code qui illustre les étapes ci-dessus :

```python
# Fonction pour enregistrer un nouvel utilisateur
import os

def register(username, password):
    try:
        if os.path.exists('credentials.txt'):
            with open('credentials.txt', 'r') as file:
                for line in file.readlines():
                    if line.startswith(username + ':'):
                        raise ValueError("Cet utilisateur existe déjà.")

        with open('credentials.txt', 'a') as file:
            file.write(f'{username}:{password}\n')
            print("Inscription réussie !")
    except Exception as e:
        print(f'Erreur : {e}')

# Fonction pour connecter un utilisateur

def login(username, password):
    try:
        if not os.path.exists('credentials.txt'):
            raise FileNotFoundError("Le fichier d'identifiants n'existe pas.")

        with open('credentials.txt', 'r') as file:
            for line in file.readlines():
                if line.strip() == f'{username}:{password}':
                    print("Connexion réussie !")
                    return
        raise ValueError("Nom d'utilisateur ou mot de passe incorrect.")
    except Exception as e:
        print(f'Erreur : {e}')

# Tester les fonctions

register('user1', 'password1')
login('user1', 'password1')  # Attendu : Connexion réussie !
login('user1', 'wrongpassword')  # Attendu : Nom d'utilisateur ou mot de passe incorrect.
```

## Corrigé
### 1. Création du fichier avec les identifiants
- Assurez-vous que le fichier `credentials.txt` est créé et accessible.

### 2. Fonction d'inscription
- Vérifiez que l'inscription d'un utilisateur déjà existant déclenche une exception avec le message approprié.

### 3. Fonction de connexion
- Testez différents scénarios de connexion pour vous assurer que les erreurs sont correctement gérées et que les messages corrects s'affichent.

### 4. Conclusion
Dans ce TP, vous avez appris comment gérer des fichiers en Python et comment gérer les exceptions lors de l'authentification. Vous pouvez maintenant étendre ce système en ajoutant des fonctionnalités supplémentaires comme la récupération de mot de passe ou le chiffrement des mots de passe.