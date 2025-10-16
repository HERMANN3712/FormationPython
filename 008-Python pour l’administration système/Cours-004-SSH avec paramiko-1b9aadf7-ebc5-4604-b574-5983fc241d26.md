# Formation : Python pour l’administration système

## Cours 004 : SSH avec Paramiko

### Objectifs de la formation
- Comprendre le protocole SSH et son utilisation en administration système.
- Apprendre à utiliser la bibliothèque Paramiko pour automatiser les connexions SSH.
- Savoir exécuter des commandes à distance sur des serveurs via SSH.

---

### Plan de la formation
1. **Introduction à SSH**  
   1.1. Qu'est-ce que SSH ?  
   1.2. Importance de SSH dans l'administration système  
   1.3. Différence entre SSH et autres protocoles comme Telnet  

2. **Présentation de Paramiko**  
   2.1. Qu'est-ce que Paramiko ?  
   2.2. Installation de Paramiko  
   2.3. Configuration de l'environnement de développement  

3. **Connexion SSH avec Paramiko**  
   3.1. Établir une connexion SSH  
   3.2. Gestion des clés SSH  
   3.3. Authentification par mot de passe vs clés  

4. **Exécution de commandes distantes**  
   4.1. Exécution de commandes simples  
   4.2. Gestion des sorties de commandes  
   4.3. Exécution de commandes en parallèle  

5. **Transfert de fichiers**  
   5.1. Utilisation de SFTP avec Paramiko  
   5.2. Upload et download de fichiers  

6. **Gestion des erreurs et débogage**  
   6.1. Gérer les exceptions courantes  
   6.2. Utilisation de logging pour le débogage  

7. **Exemple pratique**  
   7.1. Automatisation d'une tâche courante avec Paramiko  
   7.2. Mise en place d'un script complet  

8. **Conclusion et perspectives**  
   8.1. Récapitulatif des points clés  
   8.2. Ressources supplémentaires  
   8.3. Questions et réponses  

---

### Détails du contenu

#### 1. Introduction à SSH
##### 1.1. Qu'est-ce que SSH ?
SSH (Secure Shell) est un protocole réseau utilisé pour se connecter de manière sécurisée à un ordinateur distant. Il permet l'exécution de commandes, le transfert de fichiers et la gestion de sessions à distance.

##### 1.2. Importance de SSH dans l'administration système
SSH est essentiel pour les administrateurs systèmes car il assure la sécurité des communications, protège les connexions contre l'écoute, et permet l'accès à distance sécurisé. C'est un outil fondamental pour le travail sur des serveurs Linux et Unix.

##### 1.3. Différence entre SSH et autres protocoles comme Telnet
Contrairement à Telnet, qui est non sécurisé, SSH chiffre les données échangées, ce qui le rend beaucoup plus sûr pour des opérations sensibles.

#### 2. Présentation de Paramiko
##### 2.1. Qu'est-ce que Paramiko ?
Paramiko est une bibliothèque Python qui fournit l'implémentation du protocole SSH2. Elle permet de gérer les connexions SSH et SFTP de manière simple et efficace.

##### 2.2. Installation de Paramiko
Pour installer Paramiko, utilisez la commande pip :
```bash
pip install paramiko
```

##### 2.3. Configuration de l'environnement de développement
Assurez-vous d'avoir Python et pip installés sur votre machine, puis installez Paramiko comme indiqué ci-dessus.

#### 3. Connexion SSH avec Paramiko
##### 3.1. Établir une connexion SSH
```python
import paramiko

# Créez un client SSH
client = paramiko.SSHClient()
# Ajoutez la clé d'hôte (optionnel)
client.set_missing_host_key_policy(paramiko.AutoAddPolicy())

# Connectez-vous au serveur
client.connect('hostname', username='user', password='password')
```

##### 3.2. Gestion des clés SSH
Il est recommandé d'utiliser des clés SSH au lieu de mots de passe pour plus de sécurité.

##### 3.3. Authentification par mot de passe vs clés
L'authentification par clé est généralement plus sécurisée et devrait être privilégiée.

#### 4. Exécution de commandes distantes
##### 4.1. Exécution de commandes simples
```python
tout, stderr = client.exec_command('ls -l')
print(stdout.readlines())
```

##### 4.2. Gestion des sorties de commandes
Traitez les sorties et les erreurs pour mieux gérer votre script.

##### 4.3. Exécution de commandes en parallèle
Utilisez des threads ou des processus pour exécuter plusieurs commandes simultanément.

#### 5. Transfert de fichiers
##### 5.1. Utilisation de SFTP avec Paramiko
```python
sftp = client.open_sftp()
```

##### 5.2. Upload et download de fichiers
```python
sftp.put('local_file.txt', 'remote_file.txt')
```

#### 6. Gestion des erreurs et débogage
##### 6.1. Gérer les exceptions courantes
Utilisez des blocs try-except pour gérer les erreurs lors des connexions ou des commandes.

##### 6.2. Utilisation de logging pour le débogage
Paramiko peut également être configuré pour produire des logs afin de faciliter le débogage.

#### 7. Exemple pratique
##### 7.1. Automatisation d'une tâche courante avec Paramiko
Écrivez un script pour automatiser des mises à jour sur un serveur distant.

##### 7.2. Mise en place d'un script complet
Un exemple de script pour la mise à jour d'un serveur pourrait être fourni.

#### 8. Conclusion et perspectives
##### 8.1. Récapitulatif des points clés
- Importance de SSH pour la sécurité.
- Puissance de Paramiko pour automatiser les tâches.

##### 8.2. Ressources supplémentaires
Liens vers la documentation de Paramiko et d'autres ressources utiles.

##### 8.3. Questions et réponses
Session de questions/réponses pour clarifier les doutes.