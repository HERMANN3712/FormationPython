# Travaux Pratiques : Calculatrice Basique

## Objectif
L'objectif de ce travail pratique est de créer une calculatrice basique en Python. Ce TP vous aidera à comprendre les concepts de base de la programmation en Python tels que les variables, les types de données, et les fonctions.

## Pré-requis
- Avoir installé Python sur votre machine (version 3.x).
- Avoir un éditeur de texte ou un IDE (comme VSCode ou PyCharm).

## Description de l'activité
Vous allez créer une calculatrice simple qui peut effectuer des opérations de base comme l'addition, la soustraction, la multiplication, et la division.

### Étapes à suivre

1. **Création du fichier**  
   Créez un nouveau fichier nommé `calculatrice.py`.

2. **Écriture du code**  
   Dans ce fichier, écrivez le code suivant :
   
   ```python
   # Fonction pour additionner deux nombres
   def addition(a, b):
       return a + b

   # Fonction pour soustraire deux nombres
   def soustraction(a, b):
       return a - b

   # Fonction pour multiplier deux nombres
   def multiplication(a, b):
       return a * b

   # Fonction pour diviser deux nombres
   def division(a, b):
       if b == 0:
           return "Erreur: Division par zéro!"
       return a / b

   # Fonction principale
   def main():
       print("Bienvenue dans la Calculatrice Basique!")
       print("Choisissez une opération:")
       print("1. Addition")
       print("2. Soustraction")
       print("3. Multiplication")
       print("4. Division")

       choix = input("Entrez le numéro de l'opération (1-4): ")

       num1 = float(input("Entrez le premier nombre: "))
       num2 = float(input("Entrez le deuxième nombre: "))

       if choix == '1':
           print(f"Le résultat de {num1} + {num2} est {addition(num1, num2)}")
       elif choix == '2':
           print(f"Le résultat de {num1} - {num2} est {soustraction(num1, num2)}")
       elif choix == '3':
           print(f"Le résultat de {num1} * {num2} est {multiplication(num1, num2)}")
       elif choix == '4':
           print(f"Le résultat de {num1} / {num2} est {division(num1, num2)}")
       else:
           print("Erreur: Choix invalide!")

   if __name__ == '__main__':
       main()
   ```

3. **Exécution du code**  
   Enregistrez le fichier et exécutez-le dans votre terminal:
   ```bash
   python calculatrice.py
   ```
   Suivez les instructions à l'écran pour effectuer des calculs.

### Corrigé
- Les fonctions sont définies pour chacune des opérations.
- La fonction `main` permet à l'utilisateur de choisir une opération et d'entrer les nombres.
- Les résultats sont affichés à l'écran.

### Conclusion
Félicitations, vous avez créé une calculatrice basique en Python! Vous pouvez maintenant étendre ce projet en ajoutant des fonctionnalités supplémentaires, telles que la gestion des erreurs, ou même en permettant à l'utilisateur de faire des calculs successifs.