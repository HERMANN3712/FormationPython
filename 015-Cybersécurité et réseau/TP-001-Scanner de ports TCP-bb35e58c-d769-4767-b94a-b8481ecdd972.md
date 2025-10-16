# TP-001 : Scanner de Ports TCP

## Objectif
L'objectif de ce travail pratique est de développer un scanner de ports TCP simple en Python. Ce scanner vous permettra de tester la connectivité d'un service sur un hôte spécifique en vérifiant quels ports sont ouverts.

## Prérequis
Avant de commencer, assurez-vous d'avoir:
- Python installé sur votre machine (version 3.x).
- Des connaissances de base en programmation Python.

## Déroulement
1. **Créer un fichier Python**  
   Créez un fichier nommé `port_scanner.py`.

2. **Importer les bibliothèques nécessaires**  
   Vous aurez besoin de la bibliothèque `socket`. Ajoutez les lignes suivantes en haut de votre fichier :
   ```python
   import socket
   import threading
   ```

3. **Définir une fonction pour le scan des ports**  
   Créez une fonction appelée `scan_port` qui prendra un hôte et un port en paramètres et tentera de se connecter.
   ```python
   def scan_port(host, port):
       s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
       s.settimeout(1)  # délai d'attente de 1 seconde
       try:
           s.connect((host, port))
           print(f'Port {port} est ouvert')
       except:
           print(f'Port {port} est fermé')
       finally:
           s.close()
   ```

4. **Gérer plusieurs ports**  
   Créez une fonction pour gérer le scan de plusieurs ports en utilisant des threads :
   ```python
   def scan_ports(host, start_port, end_port):
       threads = []
       for port in range(start_port, end_port + 1):
           thread = threading.Thread(target=scan_port, args=(host, port))
           threads.append(thread)
           thread.start()
       for thread in threads:
           thread.join()
   ```

5. **Exécuter le scanner**  
   Ajoutez le code suivant à la fin de votre fichier pour exécuter le scanner :
   ```python
   if __name__ == '__main__':
       host = input('Entrez l\'hôte à scanner : ')
       start_port = int(input('Entrez le port de début : '))
       end_port = int(input('Entrez le port de fin : '))
       scan_ports(host, start_port, end_port)
   ```

## Tests
- Exécutez le script avec différents hôtes et plages de ports pour tester son fonctionnement.
- Essayez de scanner un hôte sur lequel vous avez le contrôle et qui a des services connus en cours d'exécution.

## Conclusion
Vous avez maintenant un scanner de ports TCP fonctionnel en Python ! Vous pouvez l'améliorer en ajoutant des fonctionnalités telles que la gestion des erreurs ou l'affichage de résultats plus détaillés.