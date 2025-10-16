# Formation : Création d’API REST

## Objectif de la formation
Cette formation vise à enseigner aux participants comment créer des API REST en utilisant Python. Nous nous concentrerons particulièrement sur la conception et l'implémentation des routes GET et POST.

## Public Cible
- Développeurs souhaitant apprendre à créer des API.
- Formateurs et professionnels en reconversion.

## Prérequis
- Connaissances de base en Python.
- Notions fondamentales sur les API et HTTP.

---

## Plan de la formation

1. **Introduction aux API REST**  
   1.1. Qu'est-ce qu'une API ?  
   1.2. Principes de REST  
   1.3. Importance des routes HTTP  
   
2. **Mise en place de l'environnement**  
   2.1. Installation des outils nécessaires (Python, Flask, etc.)  
   2.2. Configuration de l'éditeur  
   2.3. Création du projet  
   
3. **Création d'une API simple**  
   3.1. Structure du projet  
   3.2. Fichiers essentiels (app.py)  
   
4. **Routes GET**  
   4.1. Qu'est-ce qu'une route GET ?  
   4.2. Création d'une route GET avec Flask  
   4.3. Exemple pratique  
   
5. **Routes POST**  
   5.1. Qu'est-ce qu'une route POST ?  
   5.2. Création d'une route POST avec Flask  
   5.3. Exemple pratique  
   
6. **Gestion des erreurs**  
   6.1. Types d'erreurs HTTP  
   6.2. Gestion des erreurs dans Flask  
   
7. **Tests d'API**  
   7.1. Importance des tests  
   7.2. Outils de tests (Postman, unittest)  
   
8. **Déploiement de l'API**  
   8.1. Introduction au déploiement  
   8.2. Options de déploiement (Heroku, AWS)  
   
9. **Conclusion**  
   9.1. Résumé des points abordés  
   9.2. Questions/Réponses  

---

## Détails de chaque section

### 1. Introduction aux API REST
- **Qu'est-ce qu'une API ?**  
  Une API (Interface de programmation d'applications) permet aux applications de communiquer entre elles.
- **Principes de REST**  
  REST (Representational State Transfer) est un ensemble de principes d'architecture pour créer des services web.
- **Importance des routes HTTP**  
  Les routes HTTP (GET, POST, etc.) définissent comment interagir avec l'API.

### 2. Mise en place de l'environnement
#### 2.1. Installation des outils nécessaires  
- Installez Python (version 3.6 ou supérieure)  
- Installez Flask :  
```bash
pip install Flask
```
#### 2.2. Configuration de l'éditeur  
Utilisez un éditeur de texte comme VS Code ou PyCharm pour écrire le code.
#### 2.3. Création du projet  
Créez un nouveau dossier pour votre projet et un fichier nommé `app.py`.

### 3. Création d'une API simple
#### 3.1. Structure du projet  
```
MonProjet/
│
├── app.py  
└── requirements.txt  
```
#### 3.2. Fichiers essentiels  
- **app.py**  
```python
from flask import Flask  
app = Flask(__name__)  
  
if __name__ == '__main__':  
    app.run(debug=True)
```

### 4. Routes GET
#### 4.1. Qu'est-ce qu'une route GET ?  
GET est utilisé pour récupérer des données d'un serveur.
#### 4.2. Création d'une route GET avec Flask  
```python
@app.route('/api/items', methods=['GET'])  
def get_items():  
    return {'items': ['item1', 'item2', 'item3']}
```
#### 4.3. Exemple pratique  
Démarrez votre serveur et accédez à `http://127.0.0.1:5000/api/items` dans votre navigateur pour voir les résultats.

### 5. Routes POST
#### 5.1. Qu'est-ce qu'une route POST ?  
POST est utilisé pour envoyer des données au serveur.
#### 5.2. Création d'une route POST avec Flask  
```python
@app.route('/api/items', methods=['POST'])  
def create_item():  
    new_item = request.json['item']  
    return {'item': new_item}, 201
```
#### 5.3. Exemple pratique  
Utilisez Postman pour envoyer un POST à `http://127.0.0.1:5000/api/items` avec JSON.

### 6. Gestion des erreurs
#### 6.1. Types d'erreurs HTTP  
- 404 Not Found  
- 500 Internal Server Error  

#### 6.2. Gestion des erreurs dans Flask  
```python
@app.errorhandler(404)  
def not_found(error):  
    return {'error': 'Not found'}, 404
```

### 7. Tests d'API
#### 7.1. Importance des tests  
Les tests garantissent que votre API fonctionne comme prévu.
#### 7.2. Outils de tests  
- **Postman** : pour tester manuellement les requêtes  
- **unittest** : pour les tests automatisés  

### 8. Déploiement de l'API
#### 8.1. Introduction au déploiement  
Il est crucial de déployer votre API pour qu'elle soit accessible.
#### 8.2. Options de déploiement  
- **Heroku** : facile à utiliser, idéal pour les petits projets  
- **AWS** : plus complexe, évolutif pour des solutions de grande taille  

### 9. Conclusion
#### 9.1. Résumé des points abordés  
Nous avons couvert les routes GET et POST dans une API REST.
#### 9.2. Questions/Réponses  
Un temps sera alloué pour répondre aux questions des participants.

---

Merci d'avoir assisté à cette formation !