# Travail Pratique : Redémarrage Distant avec Python

## Objectif
L’objectif de ce travail pratique est d’apprendre à redémarrer un système distant en utilisant Python. Nous allons utiliser le module `paramiko` pour établir une connexion SSH et effectuer le redémarrage.

## Prérequis
- Avoir Python installé sur votre machine.
- Installer le module `paramiko`. Vous pouvez l’installer via la commande suivante :
  ```bash
  pip install paramiko
  ```
- Avoir accès à un système distant avec les informations d’identification nécessaires.

## Étapes à Suivre
### 1. Établir une Connexion SSH
Nous allons d’abord écrire un script qui établit une connexion SSH à un hôte distant.

```python
import paramiko

hostname = 'IP_DU_SERVEUR'
port = 22
username = 'VOTRE_NOM_UTILISATEUR'
password = 'VOTRE_MOT_DE_PASSE'

client = paramiko.SSHClient()
client.set_missing_host_key_policy(paramiko.AutoAddPolicy())
client.connect(hostname, port, username, password)
```

### 2. Exécuter la Commande de Redémarrage
Une fois la connexion établie, nous allons exécuter la commande de redémarrage.

```python
stdin, stdout, stderr = client.exec_command('sudo reboot')
```

### 3. Gérer les Exceptions
Il est important de gérer les exceptions pour éviter les plantages du script.

```python
try:
    client.connect(hostname, port, username, password)
    stdin, stdout, stderr = client.exec_command('sudo reboot')
    print(stdout.read().decode())
except Exception as e:
    print(f'Une erreur s’est produite : {e}')
finally:
    client.close()
```

## Script Complet
Voici le script complet que vous pouvez exécuter :

```python
import paramiko

hostname = 'IP_DU_SERVEUR'
port = 22
username = 'VOTRE_NOM_UTILISATEUR'
password = 'VOTRE_MOT_DE_PASSE'

try:
    client = paramiko.SSHClient()
    client.set_missing_host_key_policy(paramiko.AutoAddPolicy())
    client.connect(hostname, port, username, password)
    stdin, stdout, stderr = client.exec_command('sudo reboot')
    print(stdout.read().decode())
except Exception as e:
    print(f'Une erreur s’est produite : {e}')
finally:
    client.close()
```

## Conclusion
Dans ce travail pratique, nous avons appris à redémarrer un système distant en utilisant Python. Ce concept peut être appliqué à de nombreuses autres tâches d’administration système pour automatiser votre travail.