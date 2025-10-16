# Formation : Fonctions et Portée en Python  

## Objectif de la formation  
Cette formation a pour objectif de vous familiariser avec les fonctions en Python, en se concentrant sur leur définition, leur appel, ainsi que sur les notions de portée et de durée de vie des variables.


---  

## Plan de la formation  
1. **Introduction aux fonctions**  
   - Qu'est-ce qu'une fonction ?  
   - Avantages de l'utilisation des fonctions  

2. **Définir une fonction**  
   - La syntaxe de définition des fonctions  
   - Les paramètres et les arguments  
   - Valeurs de retour  
   - Exemple pratique  

3. **Appeler une fonction**  
   - Comment appeler une fonction  
   - Gestion des arguments  
   - Les arguments par défaut  
   - Exemple pratique  

4. **Portée des variables**  
   - Portée locale vs portée globale  
   - La durée de vie d'une variable  
   - Utilisation de la déclaration `global`  

5. **Conclusion et bonnes pratiques**  
   - Récapitulatif des points clés  
   - Conseils pour l'écriture de fonctions efficaces  

---  

## 1. Introduction aux fonctions  
### Qu'est-ce qu'une fonction ?  
Une fonction est un bloc de code qui effectue une tâche spécifique. Elle permet de regrouper des instructions que l'on peut réutiliser à plusieurs endroits dans le code.

### Avantages de l'utilisation des fonctions  
- **Réutilisabilité** : Écrire le code une seule fois et le réutiliser.  
- **Clarté** : Rendre le code plus lisible et compréhensible.  
- **Modularité** : Structurer le code en unités logiques.

---  

## 2. Définir une fonction  
### La syntaxe de définition des fonctions  
En Python, une fonction est définie à l'aide du mot clé `def`. Voici la syntaxe générale :  
```python  
def nom_de_la_fonction(paramètres):  
    # Corps de la fonction  
    instruction  
```  

### Les paramètres et les arguments  
- **Paramètres** : Variables définies dans la déclaration de la fonction.  
- **Arguments** : Valeurs passées à la fonction lors de son appel.  

### Valeurs de retour  
Il est possible de renvoyer une valeur à l'aide du mot clé `return`. 

### Exemple pratique  
```python  
def addition(a, b):  
    return a + b  

resultat = addition(5, 3)  
print(resultat)  # Output: 8  
```  

---  

## 3. Appeler une fonction  
### Comment appeler une fonction  
Pour appeler une fonction, utilisez son nom suivi de parenthèses contenant les arguments :  
```python  
nom_de_la_fonction(argument1, argument2)  
```  

### Gestion des arguments  
- **Arguments positionnels**: Correspondent à l'ordre des paramètres.  
- **Arguments nommés**: Passés en spécifiant le nom du paramètre.  

### Les arguments par défaut  
Il est possible de définir des valeurs par défaut pour les arguments.  

### Exemple pratique  
```python  
def salutation(nom, message="Bonjour"):  
    print(f"{message}, {nom}!")  

salutation("Alice")  # Output: "Bonjour, Alice!"  
salutation("Bob", "Salut")  # Output: "Salut, Bob!"  
```  

---  

## 4. Portée des variables  
### Portée locale vs portée globale  
- **Locale**: Variable définie à l'intérieur d'une fonction, accessible uniquement dans celle-ci.  
- **Globale**: Variable définie en dehors de toutes les fonctions, accessible partout dans le code.  

### La durée de vie d'une variable  
Une variable existe tant que son bloc d'instructions est exécuté.

### Utilisation de la déclaration `global`  
Pour modifier une variable globale à l'intérieur d'une fonction.  

---  

## 5. Conclusion et bonnes pratiques  
### Récapitulatif des points clés  
- Les fonctions permettent de structurer et réutiliser le code.  
- Comprendre la portée des variables est crucial pour éviter les erreurs.  

### Conseils pour l'écriture de fonctions efficaces  
- Écrire des fonctions courtes réalisant une seule tâche.  
- Utiliser des noms de fonctions explicites.  
- Documenter les fonctions avec des docstrings.

---  

### Ressources complémentaires  
- Documentation officielle de Python : https://docs.python.org/3/tutorial/controlflow.html#defining-functions  
- Livres recommandés : "Automate the Boring Stuff with Python" par Al Sweigart  

---  

## Fin de la formation  
Merci de votre participation!