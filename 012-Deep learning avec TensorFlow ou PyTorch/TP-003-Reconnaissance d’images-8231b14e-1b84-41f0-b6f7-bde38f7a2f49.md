# Travaux Pratiques : Reconnaissance d’Images avec TensorFlow/PyTorch

## Objectif 
L'objectif de ce travail pratique est de comprendre les bases de la reconnaissance d'images en utilisant des réseaux neuronaux avec TensorFlow ou PyTorch.

## Prérequis
- Python 3.x installé
- Bibliothèques : TensorFlow ou PyTorch, NumPy, Matplotlib, etc.

## Introduction
La reconnaissance d'images est une tâche fondamentale dans le domaine du deep learning. Au cours de ce TP, nous allons construire un modèle simple de classification d'images en utilisant le jeu de données MNIST (images de chiffres manuscrits).

## Contenu du TP
### Étape 1 : Importation des Bibliothèques
Pour commencer, importez les bibliothèques nécessaires. 

### TensorFlow
```python
import tensorflow as tf
from tensorflow.keras import layers, models
import numpy as np
import matplotlib.pyplot as plt
```

### PyTorch
```python
import torch
import torch.nn as nn
import torch.optim as optim
from torchvision import datasets, transforms
import matplotlib.pyplot as plt
```

### Étape 2 : Chargement des Données
Pour TensorFlow, vous pouvez charger le jeu de données MNIST directement comme suit :
```python
mnist = tf.keras.datasets.mnist
(x_train, y_train), (x_test, y_test) = mnist.load_data()
# Normalize les données
x_train, x_test = x_train / 255.0, x_test / 255.0
```

Pour PyTorch:
```python
transform = transforms.Compose([
    transforms.ToTensor(),
    transforms.Normalize((0.5,), (0.5,))
])
trainset = datasets.MNIST(root='./data', train=True, download=True, transform=transform)
trainloader = torch.utils.data.DataLoader(trainset, batch_size=64, shuffle=True)
```

### Étape 3 : Création du Modèle
Créez un modèle simple avec quelques couches pour la classification d'images.

**Pour TensorFlow :**
```python
model = models.Sequential([
    layers.Flatten(input_shape=(28, 28)),
    layers.Dense(128, activation='relu'),
    layers.Dense(10, activation='softmax')
])
```
**Pour PyTorch :**
```python
class NeuralNetwork(nn.Module):
    def __init__(self):
        super(NeuralNetwork, self).__init__()
        self.flatten = nn.Flatten()
        self.fc1 = nn.Linear(28*28, 128)
        self.fc2 = nn.Linear(128, 10)
        
    def forward(self, x):
        x = self.flatten(x)
        x = torch.relu(self.fc1(x))
        x = self.fc2(x)
        return x
```

### Étape 4 : Entraînement du Modèle
Pour TensorFlow :
```python
model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics=['accuracy'])
model.fit(x_train, y_train, epochs=5)
```
Pour PyTorch :
```python
model = NeuralNetwork()
loss_fn = nn.CrossEntropyLoss()
optimizer = optim.Adam(model.parameters(), lr=0.001)

for epoch in range(5):
    for batch, (X, y) in enumerate(trainloader):
        optimizer.zero_grad()
        pred = model(X)
        loss = loss_fn(pred, y)
        loss.backward()
        optimizer.step()
```

### Étape 5 : Évaluation du Modèle
Pour évaluer les performances du modèle, vous pouvez utiliser la méthode `evaluate` de TensorFlow ou effectuer une validation manuelle avec PyTorch.

**Pour TensorFlow :**
```python
test_loss, test_acc = model.evaluate(x_test, y_test)
print(f"Test accuracy: {test_acc}")
```

**Pour PyTorch :**
```python
testset = datasets.MNIST(root='./data', train=False, transform=transform)
testloader = torch.utils.data.DataLoader(testset, batch_size=64, shuffle=False)

with torch.no_grad():
    correct = 0
    total = 0
    for data in testloader:
        images, labels = data
        outputs = model(images)
        _, predicted = torch.max(outputs.data, 1)
        total += labels.size(0)
        correct += (predicted == labels).sum().item()
    print(f"Test accuracy: {100 * correct / total}%")
```

### Conclusion
Ce travail pratique vous a permis de découvrir les bases de la reconnaissance d'images, comment charger des données, créer et entraîner un modèle de réseau neuronal, et évaluer sa performance. Vous pouvez maintenant explorer des architectures plus complexes et d'autres jeux de données pour approfondir votre compréhension.