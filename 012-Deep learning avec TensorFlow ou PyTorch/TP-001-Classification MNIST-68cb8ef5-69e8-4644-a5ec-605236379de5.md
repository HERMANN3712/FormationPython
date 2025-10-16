# TP-001 : Classification MNIST avec TensorFlow / PyTorch

## Objectif
L'objectif de ce travail pratique est de comprendre les bases des réseaux neuronaux et de les appliquer à la classification d'images de chiffres manuscrits du dataset MNIST en utilisant TensorFlow ou PyTorch.

## Prérequis
- Avoir installé Python 3.x
- Installer les bibliothèques nécessaires : `tensorflow` ou `torch` et `torchvision`

## Dataset MNIST
Le dataset MNIST (Modified National Institute of Standards and Technology) contient 70 000 images de chiffres manuscrits (de 0 à 9), avec 60 000 images pour l'entraînement et 10 000 pour le test. Chaque image est en niveaux de gris et fait 28x28 pixels.

## Étapes du TP

### 1. Chargement des Bibliothèques
Pour TensorFlow :
```python
import tensorflow as tf
from tensorflow.keras import layers, models
```
Pour PyTorch :
```python
import torch
from torchvision import datasets, transforms
```

### 2. Chargement des données MNIST
Pour TensorFlow :
```python
mnist = tf.keras.datasets.mnist
(x_train, y_train), (x_test, y_test) = mnist.load_data()
```
Pour PyTorch :
```python
transform = transforms.Compose([transforms.ToTensor()])
train_set = datasets.MNIST(root='./data', train=True, download=True, transform=transform)
test_set = datasets.MNIST(root='./data', train=False, download=True, transform=transform)
```

### 3. Normalisation des données
Pour TensorFlow :
```python
x_train = x_train / 255.0
x_test = x_test / 255.0
```
Pour PyTorch :
```python
from torch.utils.data import DataLoader
train_loader = DataLoader(train_set, batch_size=64, shuffle=True)
test_loader = DataLoader(test_set, batch_size=64, shuffle=False)
```

### 4. Création du Modèle
Pour TensorFlow :
```python
model = models.Sequential([
    layers.Flatten(input_shape=(28, 28)),
    layers.Dense(128, activation='relu'),
    layers.Dense(10, activation='softmax')
])
```
Pour PyTorch :
```python
import torch.nn as nn
import torch.optim as optim

class SimpleNN(nn.Module):
    def __init__(self):
        super(SimpleNN, self).__init__()
        self.fc1 = nn.Linear(28*28, 128)
        self.fc2 = nn.Linear(128, 10)

    def forward(self, x):
        x = x.view(-1, 28*28)
        x = torch.relu(self.fc1(x))
        x = self.fc2(x)
        return x

model = SimpleNN()
```

### 5. Compilation du Modèle (pour TensorFlow uniquement)
```python
model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics=['accuracy'])
```

### 6. Entraînement du Modèle
Pour TensorFlow :
```python
model.fit(x_train, y_train, epochs=5)
```
Pour PyTorch :
```python
criterion = nn.CrossEntropyLoss()
optimizer = optim.Adam(model.parameters())

for epoch in range(5):
    for images, labels in train_loader:
        optimizer.zero_grad()
        output = model(images)
        loss = criterion(output, labels)
        loss.backward()
        optimizer.step()
```

### 7. Évaluation du Modèle
Pour TensorFlow :
```python
model.evaluate(x_test, y_test)
```
Pour PyTorch :
```python
total = 0
correct = 0
with torch.no_grad():
    for images, labels in test_loader:
        outputs = model(images)
        _, predicted = torch.max(outputs, 1)
        total += labels.size(0)
        correct += (predicted == labels).sum().item()
print('Accuracy: {:.2f}%'.format(100 * correct / total))
```

### 8. Conclusion
Vous avez maintenant réalisé un modèle simple de classification d'images à l'aide de réseaux neuronaux. A partir de cette base, vous pouvez explorer des architectures plus profondes, l'utilisation de convolutions, et d'autres techniques avancées dans le domaine du deep learning.