# TP : Calculatrice Mobile avec Kivy

## Objectif
Créer une application mobile fonctionnelle de calculatrice en utilisant Kivy, un framework Python.

## Prérequis
- Avoir Python installé (version 3.6 ou supérieure)
- Installer Kivy : `pip install kivy`
- Une compréhension de base de Python et de la programmation orientée objet.

## Étapes du TP

### 1. Création de l'environnement de travail  
  - Créez un nouveau répertoire pour votre projet.
  - Créez un fichier nommé `calculatrice.py`.

### 2. Importation des bibliothèques nécessaires  
Dans votre fichier `calculatrice.py`, commencez par importer Kivy ainsi que les autres modules nécessaires.

```python
from kivy.app import App
from kivy.uix.gridlayout import GridLayout
from kivy.uix.button import Button
from kivy.uix.textinput import TextInput
```

### 3. Création de l'interface graphique  
  - Créez une classe `Calculatrice` qui hérite de `GridLayout` pour structurer votre interface.

```python
class Calculatrice(GridLayout):
    def __init__(self, **kwargs):
        super(Calculatrice, self).__init__(**kwargs)
        self.cols = 4  # Nombre de colonnes dans votre calculatrice

        # Créer l'entrée pour afficher les calculs
        self.equation = TextInput(font_size=55, readonly=True, halign="right", multiline=False)
        self.add_widget(self.equation)

        # Ajouter les boutons de la calculatrice  
        boutons = [
            '7', '8', '9', '/',
            '4', '5', '6', '*',
            '1', '2', '3', '-',
            'C', '0', '=', '+'
        ]
        for bouton in boutons:
            self.add_widget(Button(text=bouton, on_press=self.on_button_press))

    def on_button_press(self, instance):
        if instance.text == 'C':  # Effacer l'entrée
            self.equation.text = ''
        elif instance.text == '=':  # Évaluer l'expression
            try:
                self.equation.text = str(eval(self.equation.text))
            except Exception:
                self.equation.text = 'Erreur'
        else:
            self.equation.text += instance.text  # Ajouter le bouton pressé à l'entrée
```

### 4. Démarrer l'application  
  - Créez une classe `MonApp` qui va initier l’application.

```python
class MonApp(App):
    def build(self):
        return Calculatrice()

if __name__ == '__main__':
    MonApp().run()
```

### 5. Testez votre application  
- Lancez votre application en exécutant le fichier Python :  
`python calculatrice.py`  
- Votre calculatrice devrait apparaître et être fonctionnelle.

## Corrigé  

### Structure du code  
Le code ci-dessus permet de créer une interface simple de calculatrice. Les fonctionnalités sont les suivantes :  
- Boutons numériques de 0 à 9
- Opérateurs : +, -, *, /
- Bouton égal pour évaluer l'expression
- Bouton C pour effacer l'entrée

### Conseils supplémentaires  
- Pensez à ajouter des fonctionnalités telles que la gestion des erreurs.
- Améliorez l'interface avec des styles ou des thèmes.
- Explorez l'ajout d'autres opérations ou fonctions mathématiques.

## Conclusion  
Ce TP vous permet de comprendre les bases de la création d'une application mobile avec Kivy. Vous pouvez étendre les fonctionnalités de cette calculatrice en ajoutant des fonctionnalités avancées.