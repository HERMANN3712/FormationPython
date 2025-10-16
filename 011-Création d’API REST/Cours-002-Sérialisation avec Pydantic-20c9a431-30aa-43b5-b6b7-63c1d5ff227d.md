# Formation : Création d’API REST

## Cours 002 : Sérialisation avec Pydantic

### Introduction  
La sérialisation est l'un des concepts clés dans le développement d'APIs, permettant de transformer des objets Python en formats de données (souvent JSON) qui peuvent être facilement envoyés via le réseau. Dans ce cours, nous allons explorer comment utiliser Pydantic pour faciliter la sérialisation des données dans vos applications FastAPI.

### Objectifs de la formation  
- Comprendre ce qu'est la sérialisation et pourquoi elle est importante.  
- Découvrir Pydantic et son rôle dans la sérialisation des données.  
- Apprendre à créer des modèles de données avec Pydantic.  
- Expérimenter la validation des données à l'aide de Pydantic.  

### Prérequis  
- Connaissance de base de Python.  
- Expérience préalable avec FastAPI ou d'autres frameworks web est un plus, mais pas obligatoire.  

---  

## 1. Qu'est-ce que la sérialisation ?  
La sérialisation est le processus de conversion d'objets en un format qui peut être facilement stocké ou transmis. Dans le contexte des APIs, cela signifie convertir des objets Python en JSON ou XML, qui sont les formats standard pour l'échange de données web.

### 1.1 Importance de la Sérialisation  
- Facilite l'échange de données entre le client et le serveur.  
- Permet de garantir que les données respectent le schéma prédéfini.  
- Simplifie le débogage grâce à une structure claire des données.

---  

## 2. Introduction à Pydantic  
Pydantic est une bibliothèque Python utilisée pour la validation de données et la sérialisation. Elle permet de définir des modèles de données qui vérifient automatiquement que les données reçues respectent un certain schéma.

### 2.1 Installation  
Pour installer Pydantic, utilisez pip :  
```bash  
pip install pydantic  
```

### 2.2 Fonctionnalités principales  
- Validation des données.  
- Sérialisation simple et efficace.  
- Support des types de données et des annotations.  

---  

## 3. Création de Modèles avec Pydantic  
Les modèles Pydantic sont des classes qui étendent `BaseModel`. Voici comment créer un modèle simple :

```python  
from pydantic import BaseModel

class User(BaseModel):  
    id: int  
    name: str  
    email: str
```

### 3.1 Sérialisation d’un Modèle  
Pour sérialiser un objet User, il suffit d'utiliser la méthode `.json()` :  
```python  
user = User(id=1, name='John Doe', email='john.doe@example.com')  
print(user.json())  # {"id": 1, "name": "John Doe", "email": "john.doe@example.com"}
```

### 3.2 Validation de Données  
Pydantic valide automatiquement les données lors de la création d’un modèle. Par exemple, si vous essayez de créer un utilisateur avec un email invalide :

```python  
try:  
    user = User(id='abc', name='John Doe', email='invalid-email')  
except ValueError as e:  
    print(e)
```

---  

## 4. Conclusion  
Dans ce cours, nous avons vu comment la sérialisation avec Pydantic simplifie la création et la validation de modèles de données dans une API REST. Avec Pydantic, vous pouvez être sûr que vos données respectent les schémas attendus, garantissant ainsi la robustesse de votre API.

### 4.1 Ressources Supplémentaires  
- [Documentation Pydantic](https://pydantic-docs.helpmanual.io/)  
- [FastAPI Documentation](https://fastapi.tiangolo.com/)  

