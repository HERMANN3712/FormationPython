# Formation sur la Cybersécurité et Réseau : Scan de Ports

## Introduction à la Cybersécurité
La cybersécurité est un domaine qui traite de la protection des systèmes informatiques et des réseaux contre les attaques, les dommages ou l'accès non autorisé. Cela inclut des aspects comme la sécurité des réseaux, la sécurité des applications, et la sécurité des données.

## Objectifs de la formation
1. Comprendre le concept de scan de ports.
2. Apprendre les différentes techniques de scan de ports.
3. Savoir interpréter les résultats d'un scan.
4. Explorer les outils de scan de ports.

## I. Qu'est-ce qu'un Scan de Ports ?
Un scan de ports est une technique utilisée pour déterminer quels ports d'un système informatique sont ouverts et accessibles. Les ports peuvent être considérés comme des portes d'entrée vers un système. Un scan de ports peut aider à identifier des vulnérabilités potentielles dans un réseau.

## II. Pourquoi Scanner les Ports ?
- **Évaluation de la Sécurité** : Identifier les services qui sont exposés à Internet.
- **Détection des Vulnérabilités** : Repérer les ports vulnérables pour mettre en place des mesures correctives.
- **Maintenance de Réseau** : Surveiller activement l’état des services sur le réseau.

## III. Types de Scan de Ports
1. **Scan SYN (Half-open)** : Envoie un paquet SYN pour initier une connexion. Si un paquet SYN-ACK est reçu, le port est ouvert.
2. **Scan TCP Connect** : Tente d’établir une connexion complète avec le port.
3. **Scan UDP** : Envoie des paquets UDP pour identifier les ports ouverts.
4. **Scan Stealth** : Utilise des techniques pour éviter les systèmes de détection d'intrusion.

## IV. Outils de Scan de Ports
- **Nmap** : Le plus populaire et puissant. Il permet des scans détaillés et l'identification de services.
- **Netcat** : Outil polyvalent qui peut être utilisé pour scanner et même établir des connexions.
- **Masscan** : Outil très rapide pour scanner de grands réseaux.

## V. Exemples de Scan de Ports avec Nmap
### Installation de Nmap
Pour installer Nmap, utilisez la commande suivante :
```bash
sudo apt install nmap
```

### Scan de base
Pour effectuer un scan de tous les ports d'une cible :
```bash
nmap <adresse_IP>
```

### Scan détaillé
Pour obtenir des informations détaillées sur les services en cours d’exécution :
```bash
nmap -sV -p- <adresse_IP>
```

## VI. Analyse des Résultats de Scans
- Interpréter les résultats : comprendre quels ports sont ouverts, fermés et filtrés.
- Identifier les services : savoir quels services s'exécutent sur les ports ouverts.

## VII. Conclusion
Le scan de ports est une compétence essentielle pour toute personne s'intéressant à la cybersécurité. Cela permet de mieux comprendre la sécurité d'un réseau et d'identifier les éventuels points faibles.

## VIII. Questions et Réponses
- Avez-vous des questions sur les différents types de scans ou les outils utilisés ?
- Comment pouvez-vous appliquer ces connaissances à vos propres systèmes ?

## IX. Ressources Complémentaires
- [Nmap Documentation](https://nmap.org/book/)
- [Cybrary - Network Scanning](https://www.cybrary.it/course/network-scanning/)  
- [OWASP - Port Scanning](https://owasp.org/www-community/Port_Scanning)