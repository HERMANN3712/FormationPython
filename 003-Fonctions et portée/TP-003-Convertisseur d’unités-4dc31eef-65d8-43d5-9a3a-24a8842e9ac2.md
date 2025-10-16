# Travail Pratique : Convertisseur d’unités  

## Objectif  
Maîtriser la création de fonctions pour organiser son code.

## Description  
Dans ce travail pratique, vous allez créer un convertisseur d’unités simple en Python. Ce programme permettra de convertir des unités de longueur, de masse et de température.

### Exigences  
- Le programme doit permettre de convertir :  
  - Longueur : mètres (m) en kilomètres (km)  
  - Masse : grammes (g) en kilogrammes (kg)  
  - Température : Celsius (°C) en Fahrenheit (°F)  

### Étapes à suivre  
1. **Créer une fonction pour chaque conversion**  
   - `convert_m_to_km(m)`: convertit les mètres en kilomètres.  
   - `convert_g_to_kg(g)`: convertit les grammes en kilogrammes.  
   - `convert_c_to_f(c)`: convertit les degrés Celsius en Fahrenheit.  

2. **Créer une fonction principale**  
   - `main()`: qui affichera un menu pour que l’utilisateur puisse choisir le type de conversion.

3. **Implémenter la logique de conversion**  
   - Utiliser des conditions pour diriger l’utilisateur vers la bonne fonction de conversion en fonction de son choix.

### Exemple d'utilisation  
```python
# Exemple du menu  
def main():  
    print("Choisissez le type de conversion :\n1. Mètres à Kilomètres\n2. Grammes à Kilogrammes\n3. Celsius à Fahrenheit")  
    choice = input("Entrez votre choix (1/2/3) : ")  

    if choice == "1":  
        m = float(input("Entrez la longueur en mètres : "))  
        print(f"{m} mètres = {convert_m_to_km(m)} kilomètres")  
    elif choice == "2":  
        g = float(input("Entrez le poids en grammes : "))  
        print(f"{g} grammes = {convert_g_to_kg(g)} kilogrammes")  
    elif choice == "3":  
        c = float(input("Entrez la température en Celsius : "))  
        print(f"{c} °C = {convert_c_to_f(c)} °F")  
    else:  
        print("Choix invalide")

# Appel de la fonction principale  
if __name__ == '__main__':  
    main()  
```  

### Corrigé  
```python
# Fonction de conversion  
def convert_m_to_km(m):  
    return m / 1000  


def convert_g_to_kg(g):  
    return g / 1000  


def convert_c_to_f(c):  
    return (c * 9/5) + 32  
# Fonction principale  
def main():  
    print("Choisissez le type de conversion :\n1. Mètres à Kilomètres\n2. Grammes à Kilogrammes\n3. Celsius à Fahrenheit")  
    choice = input("Entrez votre choix (1/2/3) : ")  

    if choice == "1":  
        m = float(input("Entrez la longueur en mètres : "))  
        print(f"{m} mètres = {convert_m_to_km(m)} kilomètres")  
    elif choice == "2":  
        g = float(input("Entrez le poids en grammes : "))  
        print(f"{g} grammes = {convert_g_to_kg(g)} kilogrammes")  
    elif choice == "3":  
        c = float(input("Entrez la température en Celsius : "))  
        print(f"{c} °C = {convert_c_to_f(c)} °F")  
    else:  
        print("Choix invalide")

# Appel de la fonction principale  
if __name__ == '__main__':  
    main()  
```  

## Remarques  
- Assurez-vous de tester chaque conversion pour valider le bon fonctionnement de votre programme.
- N’hésitez pas à étendre ces fonctionnalités en ajoutant d’autres conversions.