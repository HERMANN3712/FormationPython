# Formation : Deep Learning avec TensorFlow ou PyTorch  
## Cours 001 : Réseaux de Neurones (MLP)  

---  

## Objectifs de la formation  
- Comprendre les concepts fondamentaux des réseaux de neurones.  
- Construire un réseau de neurones multi-couche (MLP) à l’aide de TensorFlow ou PyTorch.  
- Évaluer les performances du modèle et effectuer des prévisions.  

## Prérequis  
- Connaissances de base en Python.  
- Connaissance de concepts de machine learning (régression, classification).  

---  

## Plan de la formation  

1. **Introduction au Deep Learning**  
   - Qu'est-ce que le Deep Learning ?  
   - Différence entre l’apprentissage supervisé et non supervisé.  
   - Applications du Deep Learning.  

2. **Concepts de Base des Réseaux de Neurones**  
   - Qu'est-ce qu'un réseau de neurones ?  
   - Perceptron : l'élément de base.  
   - Architecture d’un réseau de neurones.  
   - Fonction d’activation (sigmoïde, tanh, ReLU).  

3. **MLP - Réseaux de Neurones Multi-Couches**  
   - Principe des MLP.  
   - Propagation avant et rétropropagation.  
   - Fonction de perte et optimisation (gradient descent).  

4. **Implémentation d'un MLP avec TensorFlow**  
   - Installation de TensorFlow.  
   - Création d’un dataset.  
   - Construction d’un modèle MLP.  
   - Entraînement du modèle.  
   - Évaluation des performances.  
   - Prévisions avec le modèle.  

5. **Implémentation d'un MLP avec PyTorch**  
   - Installation de PyTorch.  
   - Création d’un dataset.  
   - Construction d’un modèle MLP.  
   - Entraînement du modèle.  
   - Évaluation des performances.  
   - Prévisions avec le modèle.  

6. **Conclusion et Perspectives**  
   - Résumé des concepts clés.  
   - Perspectives pour aller plus loin (CNN, RNN, etc.).  
   - Questions/Réponses.  

---  

## Détails des Sections  

### 1. Introduction au Deep Learning  
Le Deep Learning est une sous-catégorie du machine learning qui utilise des structures appelées réseaux de neurones pour modéliser des données complexes.  
Les réseaux de neurones peuvent apprendre des représentations à plusieurs niveaux, d'où leur nom.  

### 2. Concepts de Base des Réseaux de Neurones  
Un réseau de neurones est composé de neurones qui prennent des entrées, appliquent des poids, une fonction d’activation, puis produisent une sortie.  
Le perceptron est le modèle de base d'un neurone.  

### 3. MLP - Réseaux de Neurones Multi-Couches  
Les MLP sont constitués de plusieurs couches de neurones, où chaque couche est dépendante de la précédente.  
La rétropropagation est essentielle pour ajuster les poids selon l’erreur.  

### 4. Implémentation d'un MLP avec TensorFlow  
**Code d'Exemple :**  
```python  
import tensorflow as tf  
from sklearn.model_selection import train_test_split  
from sklearn.datasets import load_iris  

# Charger le dataset  
data = load_iris()  
X, y = data.data, data.target  
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)  

# Créer le modèle  
model = tf.keras.models.Sequential([  
    tf.keras.layers.Dense(10, activation='relu', input_shape=(X_train.shape[1],)),  
    tf.keras.layers.Dense(3, activation='softmax')  
])  

# Compiler et entraîner le modèle  
model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics=['accuracy'])  
model.fit(X_train, y_train, epochs=100)  
```  

### 5. Implémentation d'un MLP avec PyTorch  
**Code d'Exemple :**  
```python  
import torch  
import torch.nn as nn  
import torch.optim as optim  
from sklearn.model_selection import train_test_split  
from sklearn.datasets import load_iris  

# Charger le dataset  
data = load_iris()  
X, y = data.data, data.target  
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)  

# Créer un modèle  
class MLP(nn.Module):  
    def __init__(self, input_size, hidden_size, num_classes):  
        super(MLP, self).__init__()  
        self.fc1 = nn.Linear(input_size, hidden_size)  
        self.fc2 = nn.Linear(hidden_size, num_classes)  
        
    def forward(self, x):  
        x = torch.relu(self.fc1(x))  
        x = self.fc2(x)  
        return x  

model = MLP(input_size=4, hidden_size=10, num_classes=3)  
optimizer = optim.Adam(model.parameters(), lr=0.01)  

# Entraînement du modèle  
loss_function = nn.CrossEntropyLoss()  
for epoch in range(100):  
    # Opérations d'entraînement  
    # Calculer la perte, faire la rétropropagation, etc.  
```  

### 6. Conclusion et Perspectives  
Les réseaux de neurones offrent des possibilités infinies dans le domaine de l'apprentissage automatique. Cette formation a posé les bases essentielles pour comprendre et créer des MLP. Pour aller plus loin, il est recommandé d'explorer d'autres types de réseaux comme les CNN pour les images et les RNN pour les séries temporelles.