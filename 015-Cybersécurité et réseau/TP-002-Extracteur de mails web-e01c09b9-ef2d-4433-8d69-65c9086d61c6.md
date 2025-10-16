# TP : Extracteur de Mails Web

## Objectif
L'objectif de ce travail pratique est de créer un script en Python qui peut extraire les adresses e-mail d'un site web donné. Cela vous permettra de mieux comprendre l'importance de la sécurité et de l'éthique dans le domaine de la cybersécurité.

## Prérequis
- Connaissances de base en Python
- Bibliothèques Python : `requests`, `beautifulsoup4`

## Étapes à Suivre

### Étape 1 : Installation des Bibliothèques Nécessaires
Utilisez pip pour installer les bibliothèques nécessaires :
```bash
pip install requests beautifulsoup4
```

### Étape 2 : Script d'Extraction
Créez un fichier Python, par exemple `extracteur_emails.py`, et ajoutez le code suivant :
```python
import requests
from bs4 import BeautifulSoup
import re

def extract_emails(url):
    emails = set()
    try:
        response = requests.get(url)
        soup = BeautifulSoup(response.text, 'html.parser')
        # Rechercher tous les liens dans le HTML
        for link in soup.find_all('a'):
            href = link.get('href')
            # Vérifiez si le lien contient une adresse email
            if href and 'mailto:' in href:
                email = href.split(':')[1]
                emails.add(email)
        return emails
    except requests.RequestException as e:
        print(f'Erreur lors de la tentative d accès au site : {e}')
        return emails

if __name__ == '__main__':
    url = input("Entrez l'URL du site à analyser : ")
    emails = extract_emails(url)
    print("Adresses e-mail trouvées :")
    for email in emails:
        print(email)
```

### Étape 3 : Exécution du Script
- Exécutez le script et entrez l'URL d'un site web.
```bash
python extracteur_emails.py
```

### Étape 4 : Résultats
Les adresses e-mails trouvées seront affichées dans la console.

## Corrigé
Le script ci-dessus utilise la bibliothèque `requests` pour récupérer le contenu d'une page web et `BeautifulSoup` pour analyser le HTML. Il recherche des liens qui commencent par `mailto:` pour extraire les adresses e-mail.

### Considérations de Sécurité
1. **Éthique** : N'utilisez pas cet outil sur des sites web sans autorisation.
2. **Filtrage** : Considérez d'ajouter des filtres pour éviter d'extraire des adresses e-mail non valides.

### Conclusion
Ce TP vous a permis de créer un outil simple d'extraction d'adresses email, tout en soulignant l'importance de la responsabilité et de l'éthique dans le développement de scripts de test de sécurité.