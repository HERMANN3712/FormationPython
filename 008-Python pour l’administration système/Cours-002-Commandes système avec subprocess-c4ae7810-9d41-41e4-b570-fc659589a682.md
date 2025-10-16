# Formation : Python pour l’administration système

## Cours 002 : Commandes système avec subprocess

### Objectifs de la formation
- Comprendre la gestion des sous-processus en Python.
- Apprendre à exécuter des commandes système.
- Gérer les entrées/sorties des commandes.
- Traiter les erreurs lors de l’exécution des commandes.

### Prérequis
- Connaissances de base en Python.
- Notions de base sur les systèmes d’exploitation (Linux, Windows).

---

## Plan de la formation

1. **Introduction aux sous-processus**  
   1.1. Qu’est-ce qu’un sous-processus ?  
   1.2. Pourquoi utiliser le module `subprocess` ?

2. **Installation et configuration**  
   2.1. Vérification de l’installation de Python  
   2.2. Installation des bibliothèques nécessaires (si besoin)

3. **Utilisation basique du module subprocess**  
   3.1. Exécution d’une commande simple  
   3.2. Lecture de la sortie d’une commande  
   3.3. Exécution de commandes avec arguments  

4. **Avancé : gérer les entrées/sorties**  
   4.1. Rediriger la sortie d’une commande vers un fichier  
   4.2. Gérer l’entrée d’une commande  
   4.3. Communication entre processus

5. **Gestion des erreurs**  
   5.1. Catching exceptions  
   5.2. Codes de retour des commandes  
   5.3. Meilleures pratiques pour gérer les erreurs

6. **Exemples pratiques**  
   6.1. Script d’automatisation de tâches  
   6.2. Gestion de fichiers avec des commandes système  
   6.3. Surveillance de l’état du système

7. **Conclusion et Ressources**  
   7.1. Documentation officielle  
   7.2. Articles et tutoriels en ligne  
   7.3. Prochaines étapes

---

## Détails du contenu

### 1. Introduction aux sous-processus  
#### 1.1 Qu’est-ce qu’un sous-processus ?  
Un sous-processus est un processus enfant qui est créé par un processus parent. Dans le contexte d'administraties systèmes, il permet d'exécuter des commandes de la même manière que si l'on utilisait le terminal ou la ligne de commande.

#### 1.2 Pourquoi utiliser le module `subprocess` ?  
Le module `subprocess` fournit une interface pour lancer de nouveaux processus, se connecter à leur entrée/sortie et gérer leur terminal.


### 2. Installation et configuration  
#### 2.1 Vérification de l’installation de Python  
Pour vérifier que Python est installé, exécutez la commande suivante dans votre terminal :  
```bash
python --version
```
#### 2.2 Installation des bibliothèques nécessaires  
En général, `subprocess` est inclus avec les installations standard de Python. Pas besoin d'installer quoi que ce soit.


### 3. Utilisation basique du module subprocess  
#### 3.1 Exécution d’une commande simple  
Utilisez le code suivant :  
```python
import subprocess

subprocess.run(['ls', '-l'])
```
#### 3.2 Lecture de la sortie d’une commande  
Pour capturer la sortie d'une commande :  
```python
result = subprocess.run(['ls', '-l'], capture_output=True, text=True)
print(result.stdout)
```
#### 3.3 Exécution de commandes avec arguments  
```python
subprocess.run(['echo', 'Hello, World!'])
```

### 4. Avancé : gérer les entrées/sorties  
#### 4.1 Rediriger la sortie d’une commande vers un fichier  
```python
with open('output.txt', 'w') as f:
    subprocess.run(['ls', '-l'], stdout=f)
```
#### 4.2 Gérer l’entrée d’une commande  
```python
subprocess.run(['grep', 'pattern'], input='Mon texte ici', text=True)
```
#### 4.3 Communication entre processus  
Utilisez des pipes pour communiquer entre plusieurs commandes  
```python
proc1 = subprocess.Popen(['ls'], stdout=subprocess.PIPE)
proc2 = subprocess.Popen(['grep', 'pattern'], stdin=proc1.stdout, stdout=subprocess.PIPE)
```

### 5. Gestion des erreurs  
#### 5.1 Catching exceptions  
Utilisez un bloc try/except  
```python
try:
    subprocess.run(['false'], check=True)
except subprocess.CalledProcessError as e:
    print(f'Error: {e}')
```
#### 5.2 Codes de retour des commandes  
```python
result = subprocess.run(['command'], check=False)
print(result.returncode)
```
#### 5.3 Meilleures pratiques pour gérer les erreurs  
Toujours vérifier les codes de retour et gérer les exceptions.

### 6. Exemples pratiques  
#### 6.1 Script d’automatisation de tâches  
Créer un script qui exécute plusieurs commandes en séquence.
#### 6.2 Gestion de fichiers avec des commandes système  
Exemple de création et de suppression de fichiers.
#### 6.3 Surveillance de l’état du système  
Par exemple, vérifier la mémoire ou l'utilisation du processeur.

### 7. Conclusion et Ressources  
#### 7.1 Documentations officielles  
- [Documentation Python](https://docs.python.org/3/library/subprocess.html)
#### 7.2 Articles et tutoriels en ligne  
- [Real Python: Working with subprocess](https://realpython.com/python-subprocess/)  
#### 7.3 Prochaines étapes  
Encourager les participants à explorer davantage le module `subprocess` et créer leurs propres scripts.