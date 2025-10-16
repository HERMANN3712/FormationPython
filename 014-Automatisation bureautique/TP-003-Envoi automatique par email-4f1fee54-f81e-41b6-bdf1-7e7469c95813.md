# TP-003: Envoi Automatique par Email

## Objectif
L'objectif de ce travail pratique est d'apprendre à automatiser l'envoi d'emails à l'aide de Python.

## Prérequis
- Connaissance de base en Python
- Installation de la bibliothèque `smtplib`
- Accès à un serveur SMTP (comme Gmail ou un autre service d'email)

## Étapes du TP

### 1. Configuration de l'environnement

Assurez-vous d'avoir la bibliothèque nécessaire installée. Vous pouvez l'installer avec pip:

```bash
pip install secure-smtplib
```

### 2. Création du Script d'Envoi d'Email

Voici un exemple de code pour envoyer un email:

```python
import smtplib
from email.mime.multipart import MIMEMultipart
from email.mime.text import MIMEText

# Configuration des paramètres de l'email
smtp_server = 'smtp.gmail.com'
port = 587  # Pour le starttls
username = 'votre_email@gmail.com'
password = 'votre_mot_de_passe'

# Création du message
msg = MIMEMultipart()
msg['From'] = username
msg['To'] = 'destinataire@example.com'
msg['Subject'] = 'Objet de lEmail'

# Corps de l'email
body = 'Bonjour,\n\nCeci est un email envoyé automatiquement par Python!'
msg.attach(MIMEText(body, 'plain'))

# Envoi de l'email
try:
    server = smtplib.SMTP(smtp_server, port)
    server.starttls()  # Inscription au protocole TLS
    server.login(username, password)
    server.send_message(msg)
    print('Email envoyé avec succès!')
except Exception as e:
    print(f'Erreur: {e}')
finally:
    server.quit()
```

### 3. Exécution du script

- Remplacez les valeurs dans `username`, `password` et `msg['To']` par vos informations personnelles.
- Exécutez le script en utilisant la commande:

```bash
python votre_script.py
```

### 4. Questions de Réflexion
- Quel est l'impact de l'automatisation sur l'envoi d'emails dans un contexte professionnel?
- Quelles autres tâches administratives pourraient être automatisées?

## Correction

Le script ci-dessus permet d'envoyer un email via un serveur SMTP. Les étudiants doivent s'assurer que leurs configurations sont correctes et que le port est ouvert. Ils doivent également gérer les erreurs potentielles lors de l'envoi. Après l'exécution, l'élève devrait être capable de:
1. Comprendre les bases de l'envoi d'emails par SMTP.
2. Modifier le contenu des emails selon les besoins.
3. Identifier des scénarios d'automatisation dans leur propre travail.