# TP-002 : Surveillance de disque avec Python

## Introduction

Dans ce travail pratique, nous allons apprendre à créer un script Python pour surveiller l'utilisation de l'espace disque sur un serveur. L'objectif est d'automatiser la surveillance de l'espace disque et d'envoyer des alertes lorsque l'utilisation dépasse un certain seuil.

## Prérequis
- Python 3.x installé
- Module `psutil` installé (vous pouvez l'installer avec `pip install psutil`)

## Objectifs
- Vérifier l'utilisation de l'espace disque
- Alerter en cas de dépassement d'un seuil d'utilisation

## Étapes

### Étape 1 : Importer les modules nécessaires

Créez un nouveau fichier Python et commencez par importer le module `psutil`.

```python
import psutil
import smtplib
from email.mime.text import MIMEText
```

### Étape 2 : Vérifier l'utilisation du disque

Utilisez `psutil.disk_usage` pour obtenir des informations sur l'utilisation du disque.

```python
# Obtenir les informations sur l'utilisation du disque
usage = psutil.disk_usage('/')

# Afficher l'utilisation du disque
print(f'Total: {usage.total // (2**30)} GiB')
print(f'Utilisé: {usage.used // (2**30)} GiB')
print(f'Libre: {usage.free // (2**30)} GiB')
print(f'Pourcentage utilisé: {usage.percent}%')
```

### Étape 3 : Configurer l'alerte par email

Configurez une fonction pour envoyer un email d'alerte si l'utilisation du disque dépasse un certain seuil.

```python
def send_alert(percent_used):
    msg = MIMEText(f'Alerte: L'utilisation du disque a atteint {percent_used}%')
    msg['Subject'] = 'Alerte de surveillance de disque'
    msg['From'] = 'votre-email@example.com'
    msg['To'] = 'destinataire@example.com'

    # Envoi de l'email
    with smtplib.SMTP('smtp.example.com') as server:
        server.login('votre-email@example.com', 'votre_mot_de_passe')
        server.send_message(msg)
```

### Étape 4 : Mettre en place une condition d'alerte

Incluez une condition pour vérifier si l'utilisation du disque dépasse un seuil donné (par exemple 80%).

```python
if usage.percent >= 80:
    send_alert(usage.percent)
```

### Étape 5 : Lancer le script

Ajoutez un code pour exécuter le script. 

```python
if __name__ == '__main__':
    # Vérifier l'utilisation du disque
    usage = psutil.disk_usage('/')
    print(f'Pourcentage utilisé: {usage.percent}%')
    if usage.percent >= 80:
        send_alert(usage.percent)
```

## Conclusion

Vous avez créé un script qui surveille l'utilisation de l'espace disque et envoie des alertes par email lorsque le seuil est dépassé. Vous pouvez exécuter ce script via une tâche cron pour une exécution régulière.

## Corrigé
1. Importez les modules nécessaires : `psutil` et `smtplib`.
2. Vérifiez l'utilisation du disque avec `psutil.disk_usage('/')`.
3. Configurez la fonction `send_alert` pour envoyer un email lorsque le seuil est dépassé.
4. Utilisez une condition pour vérifier si le pourcentage utilisé est supérieur ou égal à 80%.
5. Exécutez le script pour tester son fonctionnement.