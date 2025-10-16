# Travail Pratique : Visualisation de la Frontière de Décision avec Scikit-Learn

## Objectif
L'objectif de ce travail pratique est de comprendre comment visualiser la frontière de décision d'un modèle de classification en utilisant la bibliothèque Scikit-Learn. Nous allons entraîner un modèle simple sur un jeu de données, puis visualiser la frontière de décision qui sépare les différentes classes.

## Prérequis
- Python installé sur votre machine
- Bibliothèques suivantes : scikit-learn, numpy, matplotlib

## Étapes

### 1. Importation des bibliothèques nécessaires
```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.datasets import make_moons
from sklearn.model_selection import train_test_split
from sklearn.svm import SVC
```

### 2. Création des données
Nous allons créer un jeu de données en forme de lune (moons) pour notre démonstration.
```python
X, y = make_moons(n_samples=100, noise=0.1, random_state=42)
```

### 3. Séparation du jeu de données
Nous allons diviser notre jeu de données en ensembles d'entraînement et de test.
```python
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

### 4. Entraînement du modèle
Nous utiliserons un SVM (Support Vector Machine) pour l'entraînement.
```python
model = SVC(kernel='rbf')
model.fit(X_train, y_train)
```

### 5. Visualisation de la frontière de décision
Nous allons créer une fonction pour visualiser la frontière de décision du modèle.
```python
def plot_decision_boundary(X, y, model):
    # Définir les limites de l'axe
    x_min, x_max = X[:, 0].min() - 1, X[:, 0].max() + 1
    y_min, y_max = X[:, 1].min() - 1, X[:, 1].max() + 1
    xx, yy = np.meshgrid(np.arange(x_min, x_max, 0.01), np.arange(y_min, y_max, 0.01))
    Z = model.predict(np.c_[xx.ravel(), yy.ravel()])
    Z = Z.reshape(xx.shape)
    plt.contourf(xx, yy, Z, alpha=0.8)
    plt.scatter(X[:, 0], X[:, 1], c=y, edgecolors='k', marker='o')
    plt.title('Frontière de Décision SVM')
    plt.xlabel('Feature 1')
    plt.ylabel('Feature 2')
    plt.show()

plot_decision_boundary(X_train, y_train, model)
```

### 6. Exécution du code
Vous pouvez exécuter le code ci-dessus dans votre environnement Python pour visualiser la frontière de décision du modèle SVM.

## Corrigé
Votre code doit produire une visualisation de la frontière de décision, avec des points représentant les données de votre jeu d'entraînement. Assurez-vous que les couleurs des zones de la frontière de décision correspondent aux classes des points de données.

### Résultat attendu
- Une figure qui montre la frontière de décision avec les classes bien séparées.

## Conclusion
Dans ce travail pratique, nous avons appris à visualiser la frontière de décision d'un modèle SVM sur un jeu de données en forme de lune. Cette technique peut être appliquée à d'autres modèles et jeux de données pour mieux comprendre comment le modèle apprend à classifier les données.