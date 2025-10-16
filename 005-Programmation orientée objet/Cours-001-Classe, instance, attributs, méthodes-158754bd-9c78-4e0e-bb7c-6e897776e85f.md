# Formation sur la Programmation Orientée Objet en Python

## Objectif de la Formation
Cette formation vise à introduire les concepts fondamentaux de la programmation orientée objet (POO) en Python, en mettant l'accent sur les classes, les instances, les attributs et les méthodes.

## Plan de la Formation
1. **Introduction à la Programmation Orientée Objet**  
   - Qu'est-ce que la POO ?  
   - Avantages de la POO  

2. **Les Classes**  
   - Définition d'une classe  
   - Syntaxe de déclaration d'une classe  
   - Exemple simple de classe  

3. **Les Instances**  
   - Qu'est-ce qu'une instance ?  
   - Création d'instances  
   - Utilisation des instances  

4. **Attributs**  
   - Qu'est-ce qu'un attribut ?  
   - Attributs d'instance vs Attributs de classe  
   - Comment définir et utiliser des attributs  

5. **Méthodes**  
   - Qu'est-ce qu'une méthode ?  
   - Définir des méthodes au sein d'une classe  
   - Méthodes d'instance vs Méthodes de classe  

6. **Héritage et Polymorphisme (Bref Introduction)**  
   - Qu'est-ce que l'héritage ?  
   - Le polymorphisme en POO  

7. **Conclusion et Ressources**  
   - Récapitulatif des concepts  
   - Ressources supplémentaires pour approfondir  

---

## 1. Introduction à la Programmation Orientée Objet
La programmation orientée objet est un paradigme de programmation qui se base sur le concept d'objets, qui peuvent contenir des données sous forme de champs (attributs) et du code sous forme de procédures (méthodes).  
Il s'agit d'un moyen efficace de structurer un programme pour le rendre plus compréhensible et modulable.

### Avantages de la POO
- **Réutilisabilité** : Les classes peuvent être réutilisées pour créer de nouvelles classes.  
- **Modularité** : Le code est organisé en classes qui contiennent des méthodes et des attributs.  
- **Simplicité** : Les concepts de la POO sont plus intuitifs pour modéliser des problèmes du monde réel.

## 2. Les Classes
### Définition d'une classe
Une classe est une structure qui définit des attributs et des méthodes que ses instances peuvent avoir.

### Syntaxe de déclaration d'une classe
```python
class NomDeLaClasse:
    pass  # initialisation de la classe sans méthode ni attribut
```

### Exemple simple de classe
```python
class Chien:
    def __init__(self, nom, age):  # méthode constructeur
        self.nom = nom
        self.age = age
    
    def aboyer(self):  # méthode du chien
        print("Woof!")
```

## 3. Les Instances
### Qu'est-ce qu'une instance ?
Une instance est un objet créé à partir d'une classe. Chaque instance peut avoir des valeurs différentes pour ses attributs.

### Création d'instances
```python
mon_chien = Chien(nom='Rex', age=5)
```

### Utilisation des instances
```python
print(mon_chien.nom)  # Affiche 'Rex'
mon_chien.aboyer()  # Affiche 'Woof!'
```

## 4. Attributs
### Qu'est-ce qu'un attribut ?
Un attribut est une variable qui appartient à une classe ou à une instance.

### Attributs d'instance vs Attributs de classe
- **Attributs d'instance** : Spécifiques à chaque instance.  
- **Attributs de classe** : Partagés par toutes les instances d'une classe.

### Définir et utiliser des attributs
```python
class Chien:
    espece = 'Canis lupus familiaris'  # attribut de classe

    def __init__(self, nom, age):
        self.nom = nom  # attribut d'instance
        self.age = age
```

## 5. Méthodes
### Qu'est-ce qu'une méthode ?
Une méthode est une fonction définie dans une classe qui peut agir sur ses attributs.

### Définir des méthodes au sein d'une classe
```python
class Chien:
    def aboyer(self):
        print(f"{self.nom} dit Woof!")
```

### Méthodes d'instance vs Méthodes de classe
- **Méthodes d'instance** : Agissent sur une instance.
- **Méthodes de classe** : Utilisées pour accéder aux attributs de classe.

## 6. Héritage et Polymorphisme (Bref Introduction)
### Qu'est-ce que l'héritage ?
L'héritage permet de créer une nouvelle classe à partir d'une classe existante.

### Le polymorphisme en POO
Le polymorphisme permet d'utiliser des objets de différentes classes de la même manière.

## 7. Conclusion et Ressources
### Récapitulatif des concepts
La programmation orientée objet permet une structuration efficace du code en utilisant des classes, des instances, des attributs et des méthodes.

### Ressources supplémentaires pour approfondir
- [Documentation officielle Python](https://docs.python.org/3/tutorial/classes.html)
- [OpenClassrooms - Programmation orientée objet](https://openclassrooms.com/fr/courses/6175841-initiez-vous-a-la-programmation-orientee-objet-avec-python)
