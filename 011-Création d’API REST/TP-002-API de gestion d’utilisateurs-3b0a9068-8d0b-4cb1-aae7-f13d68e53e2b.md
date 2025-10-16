# Travail Pratique : API de Gestion d'Utilisateurs

## Objectif
Créer une API REST simple pour gérer des utilisateurs, en utilisant Flask ou FastAPI.

## Prérequis
- Connaissances de base en Python
- Connaissance de Flask ou FastAPI
- Installation de Flask ou FastAPI en fonction de votre choix

## Étapes du TP

### 1. Création de l'environnement

Créez un environnement virtuel et installez Flask ou FastAPI.

```bash
# Pour Flask
python -m venv venv
source venv/bin/activate # Pour Linux/Mac
venv\Scripts\activate  # Pour Windows
pip install Flask

# Pour FastAPI
python -m venv venv
source venv/bin/activate # Pour Linux/Mac
venv\Scripts\activate  # Pour Windows
pip install fastapi uvicorn
```

### 2. Création de l'application

#### Pour Flask

Créez un fichier `app.py` et ajoutez le code suivant :

```python
from flask import Flask, jsonify, request

app = Flask(__name__)

users = []

@app.route('/users', methods=['GET'])
def get_users():
    return jsonify(users)

@app.route('/users', methods=['POST'])
def add_user():
    user = request.json
    users.append(user)
    return jsonify(user), 201

@app.route('/users/<int:user_id>', methods=['GET'])
def get_user(user_id):
    user = next((user for user in users if user.get('id') == user_id), None)
    if user:
        return jsonify(user)
    return jsonify({'message': 'User not found'}), 404

if __name__ == '__main__':
    app.run(debug=True)
```

#### Pour FastAPI

Créez un fichier `main.py` et ajoutez le code suivant :

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class User(BaseModel):
    id: int
    name: str

users = []

@app.get('/users')
def get_users():
    return users

@app.post('/users')
def add_user(user: User):
    users.append(user.dict())
    return user

@app.get('/users/{user_id}')
def get_user(user_id: int):
    user = next((user for user in users if user['id'] == user_id), None)
    if user:
        return user
    return {'message': 'User not found'}

if __name__ == '__main__':
    import uvicorn
    uvicorn.run(app, host='127.0.0.1', port=8000)
```

### 3. Tester l'API

Utilisez `curl` ou Postman pour tester votre API.

- **Ajouter un utilisateur:**  
```bash
curl -X POST http://localhost:5000/users -H "Content-Type: application/json" -d '{"id": 1, "name": "John Doe"}'
```

- **Obtenir tous les utilisateurs:**  
```bash
curl -X GET http://localhost:5000/users
```

- **Obtenir un utilisateur par ID:**  
```bash
curl -X GET http://localhost:5000/users/1
```

### 4. Corrigé

Le code ci dessus pour Flask et FastAPI constitue une solution fonctionnelle pour créer une API de gestion d'utilisateurs. Les points essentiels de l'API sont :
- Ajout d'utilisateurs
- Récupération de tous les utilisateurs
- Récupération d'un utilisateur spécifique par son ID

N'hésitez pas à expérimenter avec l'API en ajoutant des fonctionnalités comme la mise à jour et la suppression d'utilisateurs.