# Formation: Introduction à Python

## Cours 003: Variables et types de base

### Objectifs du cours
- Comprendre le concept de variables en Python.
- Connaître les différents types de base en Python.
- Savoir comment déclarer et utiliser des variables.

---

## 1. Introduction aux variables

Les **variables** sont des espaces de stockage qui ont un nom et peuvent contenir des données. En Python, les variables sont dynamiquement typées, ce qui signifie que vous n’avez pas besoin de déclarer le type de la variable au préalable.

### 1.1 Déclaration de variables

Pour créer une variable, il suffit de lui donner un nom et de lui assigner une valeur.

```python
x = 10
nom = "Jean"
```

### 1.2 Nommage des variables

Les noms de variable doivent respecter certaines règles :
- Ils ne peuvent pas commencer par un chiffre.
- Ils ne peuvent contenir que des lettres, des chiffres et des underscores (_).
- Ils sont sensibles à la casse (par exemple, `Nom` et `nom` sont différents).

---

## 2. Types de base en Python

Python possède plusieurs types de données de base. Les plus courants incluent :

### 2.1 Nombres

Les nombres en Python peuvent être des entiers, des flottants (décimaux) ou des complexes.

- **Entiers** :
  ```python
  entier = 42
  ```

- **Flottants** :
  ```python
  flottant = 3.14
  ```

- **Complexes** :
  ```python
  complexe = 1 + 2j
  ```

### 2.2 Chaînes de caractères

Les chaînes sont des séquences de caractères et peuvent être définies avec des guillemets simples (`'`) ou doubles (`"`).

```python
chaine = "Bonjour, monde!"
```

### 2.3 Booléens

Les valeurs booléennes peuvent être soit `True` soit `False`.

```python
est_vrai = True
```

---

## 3. Utilisation des variables

Les variables peuvent être utilisées dans des opérations, affichées à l'écran, ou modifiées.

### 3.1 Affichage des variables

Pour afficher le contenu d'une variable, utilisez la fonction `print()` :

```python
print(nom)  # Affiche: Jean
```

### 3.2 Modifier les variables

Vous pouvez changer la valeur d'une variable simplement en lui assignant une nouvelle valeur :

```python
x = 5  # Changement de la valeur
```

---

## 4. Conclusion

Les variables et les types de base sont fondamentaux pour la programmation en Python. Ils vous permettent de stocker et de manipuler des données. Dans les prochaines leçons, nous allons explorer des concepts plus avancés et comment utiliser ces variables dans des structures de contrôle.

---

## Exercices pratiques

1. Créez une variable pour votre nom et utilisez la fonction `print()` pour l'afficher.
2. Déclarez une variable de type entier, une de type flottant et une de type chaîne, puis affichez toutes les valeurs.
3. Modifiez la valeur de votre variable entière et affichez-la à nouveau.