# Travail Pratique : Calcul de Factorielle

## Objectif
L'objectif de ce travail pratique est d'apprendre à créer et utiliser des fonctions en Python pour résoudre un problème concret, en l'occurrence le calcul de la factorielle d'un nombre.

## Contexte
La factorielle d'un nombre entier positif n (noté n!) est le produit de tous les entiers positifs inférieurs ou égaux à n. Par exemple :
- 5! = 5 × 4 × 3 × 2 × 1 = 120
- 0! = 1 (par définition)

## Exercice
1. **Création de la fonction :** Écrivez une fonction nommée `factorielle` qui prend un seul argument entier `n` et retourne la valeur de n!.  
   - Si `n` est négatif, la fonction doit retourner `None`.
2. **Gestion des entrées utilisateur :** Utilisez la fonction pour demander à l'utilisateur un nombre entier et affichez le résultat de la factorielle.
3. **Tests :** Effectuez des tests avec différents nombres pour vérifier que votre fonction fonctionne correctement.

### Exemple d'utilisation
```python
# Exemple de définition de la fonction

def factorielle(n):
    if n < 0:
        return None
    elif n == 0:
        return 1
    else:
        resultat = 1
        for i in range(1, n + 1):
            resultat *= i
        return resultat

# Utilisation de la fonction
nombre = int(input("Entrez un nombre entier : "))
resultat = factorielle(nombre)
if resultat is not None:
    print(f"La factorielle de {nombre} est {resultat}")
else:
    print("La factorielle n'est pas définie pour les nombres négatifs.")
```

## Corrigé
Voici une proposition de solution pour le travail pratique :

```python
def factorielle(n):
    if n < 0:
        return None
    elif n == 0:
        return 1
    else:
        resultat = 1
        for i in range(1, n + 1):
            resultat *= i
        return resultat

nombre = int(input("Entrez un nombre entier : "))
resultat = factorielle(nombre)
if resultat is not None:
    print(f"La factorielle de {nombre} est {resultat}")
else:
    print("La factorielle n'est pas définie pour les nombres négatifs.")
```

### Remarques
- Vérifiez que votre fonction gère bien le cas des nombres négatifs.
- Pensez à tester des cas limites comme 0 et 1 pour s'assurer que votre fonction fonctionne correctement.

## Conclusion
Ce travail pratique vous a permis de mieux comprendre comment créer des fonctions en Python et comment les utiliser pour résoudre des problèmes concrets.