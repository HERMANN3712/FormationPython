# Travail Pratique : Analyse de Texte

## Objectifs du TP
L'objectif de ce TP est de vous familiariser avec les structures de données en Python, notamment les listes, les tuples, les dictionnaires et les ensembles, à travers l'analyse d'un texte.

## Contexte
Vous allez analyser un texte pour en extraire des informations pertinentes telles que le nombre de mots, la fréquence des mots et les mots uniques. Vous utiliserez les structures de données de Python pour stocker et traiter ces informations.

## Instructions
1. **Chargement du texte**
   - Créez une fonction `charger_texte(chemin)` qui lit le contenu d'un fichier texte et le renvoie sous forme de chaîne.

2. **Analyse du texte**
   - Créez une fonction `analyser_texte(texte)` qui effectue les opérations suivantes :
     - Comptez le nombre total de mots.
     - Trouvez la fréquence de chaque mot. Utilisez un dictionnaire pour stocker cette information.
     - Identifiez et listez les mots uniques en utilisant un ensemble.

3. **Affichage des résultats**
   - Créez une fonction `afficher_resultats(frequence_mots)` qui affiche la fréquence des mots de manière lisible.

## Exigences
- Utilisez au moins deux types de structures de données différentes dans votre code.
- Commentez votre code pour expliquer chaque partie.
- Testez votre code avec un fichier texte de votre choix.

## Exemple de fichier texte
Pour vous aider, vous pouvez utiliser le texte suivant :
```
Dans un village paisible, un chat noir se promenait dans les rues. Un jour, il a rencontré un chien. Ils sont devenus amis.
```

## Corrigé
Voici un exemple de solution au travail pratique ci-dessus :

```python
# Charges le texte à partir d'un fichier

def charger_texte(chemin):
    with open(chemin, 'r') as fichier:
        return fichier.read()

# Analyser le texte

def analyser_texte(texte):
    mots = texte.split()
    total_mots = len(mots)
    frequence = {}
    mots_uniques = set(mots)

    for mot in mots:
        if mot in frequence:
            frequence[mot] += 1
        else:
            frequence[mot] = 1

    return total_mots, frequence, mots_uniques

# Afficher les résultats

def afficher_resultats(frequence_mots):
    for mot, count in frequence_mots.items():
        print(f'{mot}: {count}')

# Main
if __name__ == '__main__':
    chemin_fichier = 'chemin/vers/votre/fichier.txt'
    texte = charger_texte(chemin_fichier)
    total_mots, frequence, mots_uniques = analyser_texte(texte)
    print(f'Nombre total de mots: {total_mots}')
    print('Fréquence des mots:')
    afficher_resultats(frequence)
    print(f'Mots uniques: {mots_uniques}')
```

## Conclusion
Ce TP vous a permis de mettre en pratique vos connaissances sur les structures de données en Python à travers l'analyse de texte, une tâche courante en traitement de données.