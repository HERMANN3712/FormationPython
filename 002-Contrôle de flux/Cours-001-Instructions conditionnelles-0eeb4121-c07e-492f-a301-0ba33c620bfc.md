# Formation sur le Contrôle de Flux en Python : Instructions Conditionnelles

## Introduction  
Le contrôle de flux est un concept fondamental en programmation, permettant de diriger l'exécution du code en fonction de certaines conditions. 
Dans ce module, nous allons explorer les instructions conditionnelles en Python, qui sont essentielles pour prendre des décisions au sein de nos programmes.

## Plan de la Formation  
1. [Introduction aux instructions conditionnelles](#introduction-aux-instructions-conditionnelles)  
2. [L'Instruction `if`](#linstruction-if)  
   - 2.1 [Syntaxe de base](#syntaxe-de-base)  
   - 2.2 [Exemples](#exemples)  
3. [L'Instruction `if...else`](#linstruction-ifelse)  
   - 3.1 [Syntaxe et utilisation](#syntaxe-et-utilisation)  
   - 3.2 [Exemples](#exemples-1)  
4. [L'Instruction `elif`](#linstruction-elif)  
   - 4.1 [Quand l'utiliser](#quand-lutiliser)  
   - 4.2 [Exemples](#exemples-2)  
5. [Conditions imbriquées](#conditions-imbriquées)  
   - 5.1 [Comment fonctionnent les conditions imbriquées](#comment-fonctionnent-les-conditions-imbriquées)  
   - 5.2 [Exemples](#exemples-3)  
6. [Opérateurs de comparaison et logiques](#operateurs-de-comparaison-et-logiques)  
7. [Conclusion](#conclusion)  

## Introduction aux instructions conditionnelles  
Les instructions conditionnelles sont des constructions qui permettent de déterminer si une condition donnée est vraie ou fausse. En fonction du résultat, nous pouvons exécuter différentes parties de code. 

## L'Instruction `if`  
### Syntaxe de base  
```python  
if condition:  
    # code à exécuter si la condition est vraie  
```  
### Exemples  
```python  
age = 18  
if age >= 18:  
    print("Vous êtes majeur.")  
```  

## L'Instruction `if...else`  
### Syntaxe et utilisation  
```python  
if condition:  
    # code à exécuter si la condition est vraie  
else:  
    # code à exécuter si la condition est fausse  
```  
### Exemples  
```python  
age = 16  
if age >= 18:  
    print("Vous êtes majeur.")  
else:  
    print("Vous êtes mineur.")  
```  

## L'Instruction `elif`  
### Quand l'utiliser  
L'instruction `elif` permet d'ajouter une ou plusieurs alternatives à une structure conditionnelle.  
### Exemples  
```python  
note = 15  
if note >= 18:  
    print("Mention Très Bien")  
elif note >= 14:  
    print("Mention Bien")  
else:  
    print("Pas de mention")  
```  

## Conditions imbriquées  
### Comment fonctionnent les conditions imbriquées  
On peut imbriquer des instructions conditionnelles pour vérifier des conditions supplémentaires à l'intérieur d'autres conditions.  
### Exemples  
```python  
age = 20  
pays = "France"  
if age >= 18:  
    if pays == "France":  
        print("Vous êtes majeur en France.")  
    else:  
        print("Vous êtes majeur mais pas en France.")  
else:  
    print("Vous êtes mineur.")  
```  

## Opérateurs de comparaison et logiques  
Les opérateurs de comparaison tels que `==`, `!=`, `>`, `<`, `>=`, `<=` et les opérateurs logiques `and`, `or`, `not` sont souvent utilisés dans les instructions conditionnelles.  
### Exemples  
```python  
nombre = 10  
if nombre > 5 and nombre < 15:  
    print("Le nombre est entre 5 et 15.")  
```  

## Conclusion  
Les instructions conditionnelles sont un élément clé de la logique de programmation. Elles nous permettent de diriger notre code en fonction des valeurs et des conditions, rendant nos programmes interactifs et réactifs.