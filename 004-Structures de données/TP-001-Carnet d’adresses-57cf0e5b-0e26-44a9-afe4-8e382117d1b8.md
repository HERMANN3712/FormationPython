# Travail Pratique : Carnet d'adresses

## Objectif
L'objectif de ce travail pratique est de vous familiariser avec les structures de données en Python en créant un carnet d'adresses. Vous allez devoir manipuler des collections de données, comme des listes et des dictionnaires, pour stocker et gérer des informations sur vos contacts.

## Description du TP
Dans ce TP, vous allez créer une application simple de carnet d'adresses qui permettra d'ajouter, de rechercher et d'afficher des contacts.

### Étapes à suivre

1. **Initialisation**  
   Créez un dictionnaire qui servira de carnet d'adresses.
   ```python
   carnet_d_adresses = {}
   ```

2. **Fonction pour ajouter un contact**  
   Créez une fonction `ajouter_contact` qui prendra comme paramètres le nom, le numéro de téléphone et l'adresse e-mail d'un contact. Cette fonction ajoutera le contact au carnet d'adresses.
   ```python
   def ajouter_contact(nom, telephone, email):
       carnet_d_adresses[nom] = {'telephone': telephone, 'email': email}
   ```

3. **Fonction pour rechercher un contact**  
   Créez une fonction `rechercher_contact` qui prendra un nom comme paramètre. Cette fonction retournera les informations du contact si celui-ci existe, ou un message d'erreur sinon.
   ```python
   def rechercher_contact(nom):
       return carnet_d_adresses.get(nom, 'Contact non trouvé')
   ```

4. **Fonction pour afficher tous les contacts**  
   Créez une fonction `afficher_contacts` qui affichera tous les contacts ainsi que leurs informations.
   ```python
   def afficher_contacts():
       for nom, infos in carnet_d_adresses.items():
           print(f'Nom: {nom}, Téléphone: {infos['telephone']}, Email: {infos['email']}')
   ```

5. **Interface Utilisateur**  
   Implémentez une interface utilisateur simple qui vous permettra d'ajouter, de rechercher ou d'afficher des contacts en utilisant un menu.
   ```python
   while True:
       print('\nMenu :')
       print('1. Ajouter un contact')
       print('2. Rechercher un contact')
       print('3. Afficher tous les contacts')
       print('4. Quitter')
       choix = input('Choisissez une option : ')

       if choix == '1':
           nom = input('Nom : ')
           telephone = input('Téléphone : ')
           email = input('Email : ')
           ajouter_contact(nom, telephone, email)
       elif choix == '2':
           nom = input('Nom à rechercher : ')
           print(rechercher_contact(nom))
       elif choix == '3':
           afficher_contacts()
       elif choix == '4':
           break
       else:
           print('Option invalide. Réessayez.')
   ```

## Correction
Pour corriger ce travail, vérifiez que le code comprend toutes les étapes mentionnées ci-dessus et que chaque fonction fonctionne correctement. Testez le code avec des données d'exemple et vérifiez les résultats. Assurez-vous également que l'interface utilisateur est conviviale et que le programme gère les erreurs potentielles (comme une recherche d'un contact qui n'existe pas).

## Conclusion
À la fin de ce travail pratique, vous aurez acquis une compréhension des structures de données basiques en Python, ainsi que des compétences pour manipuler des collections de données.