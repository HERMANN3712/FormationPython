# Formation : Python pour l’administration système  
## Module : Surveillance avec psutil  

---  

### Objectif de la formation  
Cette formation vise à enseigner aux participants l'utilisation de la bibliothèque `psutil` pour surveiller et gérer les ressources système sous Python. À la fin de ce module, les participants comprendront comment utiliser `psutil` pour obtenir des informations sur les processus, l'utilisation de la mémoire, du CPU, des disques et des réseaux.

### Prérequis  
- Connaissances de base en Python.  
- Familiarité avec l’administration système.  

---  

## Plan de la formation  
1. **Introduction à psutil**  
   1.1 Qu'est-ce que psutil ?  
   1.2 Installation de psutil  
   1.3 Structure de la bibliothèque  

2. **Surveillance des processus**  
   2.1 Récupération de la liste des processus  
   2.2 Informations sur un processus spécifique  
   2.3 Filtrage et gestion des processus  

3. **Surveillance de l'utilisation de la mémoire**  
   3.1 Obtenir des informations sur la mémoire physique et virtuelle  
   3.2 Analyse de l'utilisation de la mémoire par les processus  
   3.3 Outils pour la gestion de mémoire  

4. **Surveillance de l'utilisation du CPU**  
   4.1 Obtenir l'utilisation du CPU  
   4.2 Surveillance des cœurs du CPU  
   4.3 Gestion des priorités des processus  

5. **Surveillance du disque**  
   5.1 Utilisation des disques  
   5.2 Surveillance des partitions  
   5.3 Gestion des fichiers  

6. **Surveillance réseau**  
   6.1 Informations sur les interfaces réseau  
   6.2 Surveillance des connexions réseau  
   6.3 Analyse de la bande passante  

7. **Mise en pratique**  
   7.1 Développement d'un script de surveillance complet  
   7.2 Exemples de cas d'utilisation  
   7.3 Résolution des problèmes courants  

---  

## Contenu détaillé  
### 1. Introduction à psutil  
#### 1.1 Qu'est-ce que psutil ?  
`psutil` est une bibliothèque Python qui fournit une interface pour récupérer des informations sur les processus en cours et l'utilisation des ressources système, telles que la mémoire, le CPU, le disque et le réseau.  

#### 1.2 Installation de psutil  
Pour installer `psutil`, vous pouvez utiliser pip :  
```bash  
pip install psutil  
```  

#### 1.3 Structure de la bibliothèque  
`psutil` est structuré autour de plusieurs modules qui permettent d'interagir avec différentes métriques système.\

### 2. Surveillance des processus  
#### 2.1 Récupération de la liste des processus  
Utilisation de `psutil.process_iter()` pour obtenir la liste des processus en cours.  
Exemple :  
```python  
import psutil  
for proc in psutil.process_iter(['pid', 'name']):  
    print(proc.info)  
```  

#### 2.2 Informations sur un processus spécifique  
Accéder aux informations détaillées d'un processus avec son PID.  

#### 2.3 Filtrage et gestion des processus  
Utilisation de méthodes pour filtrer, tuer ou suspendre des processus.  

### 3. Surveillance de l'utilisation de la mémoire  
#### 3.1 Obtenir des informations sur la mémoire physique et virtuelle  
Utilisation des méthodes `psutil.virtual_memory()` et `psutil.swap_memory()`.  

#### 3.2 Analyse de l'utilisation de la mémoire par les processus  
Comment évaluer l'utilisation de la mémoire par chaque processus.  

#### 3.3 Outils pour la gestion de mémoire  
Exploration des options de gestion de mémoire.  

### 4. Surveillance de l'utilisation du CPU  
#### 4.1 Obtenir l'utilisation du CPU  
Utilisation de `psutil.cpu_percent()` pour surveiller l'utilisation.  

#### 4.2 Surveillance des cœurs du CPU  
Analyser l'utilisation au niveau des cœurs.  

#### 4.3 Gestion des priorités des processus  
Comment ajuster la priorité d'un processus.  

### 5. Surveillance du disque  
#### 5.1 Utilisation des disques  
Informations sur l'espace disque disponible et utilisé.  

#### 5.2 Surveillance des partitions  
Récupération des informations sur les partitions.  

#### 5.3 Gestion des fichiers  
Manipulation de fichiers à l'aide de `psutil`.  

### 6. Surveillance réseau  
#### 6.1 Informations sur les interfaces réseau  
Utilisation de `psutil.net_if_addrs()` pour récupérer les adresses.  

#### 6.2 Surveillance des connexions réseau  
Vérification des connexions ouvertes avec `psutil.net_connections()`.  

#### 6.3 Analyse de la bande passante  
Comment mesurer l'utilisation de la bande passante.  

### 7. Mise en pratique  
#### 7.1 Développement d'un script de surveillance complet  
Création d'un script intégrant toutes les fonctionnalités de surveillance.  

#### 7.2 Exemples de cas d'utilisation  
Cas d'utilisation dans des environnements réels.  

#### 7.3 Résolution des problèmes courants  
Comment résoudre les erreurs courantes avec `psutil`.  

---  

### Méthodes pédagogiques  
- Présentations théoriques  
- Démonstrations en direct  
- Exercices pratiques  

### Conclusion  
Cette formation permet aux participants de développer une compréhension pratique de la surveillance des ressources système à l'aide de Python et de la bibliothèque `psutil`. Ils seront désormais capables de créer des outils sur mesure pour le suivi des performances de leurs systèmes.