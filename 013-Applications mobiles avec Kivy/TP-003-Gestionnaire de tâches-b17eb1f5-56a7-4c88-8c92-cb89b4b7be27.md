# Gestionnaire de Tâches avec Kivy

## Objectif
Créer une application mobile simple de gestion de tâches en utilisant Kivy, un framework Python pour le développement d'applications multi-plates-formes.

## Prérequis
- Python installé sur votre machine.
- Kivy installé via pip : `pip install kivy`

## Étapes du projet

### 1. Structure du projet
Créez un dossier pour votre projet, par exemple `gestionnaire_de_taches`, et à l'intérieur, créez un fichier `main.py`.

### 2. Code de l'application

Voici un exemple de code pour votre gestionnaire de tâches :

```python
from kivy.app import App
from kivy.uix.boxlayout import BoxLayout
from kivy.uix.button import Button
from kivy.uix.textinput import TextInput
from kivy.uix.label import Label
from kivy.uix.scrollview import ScrollView
from kivy.uix.stacklayout import StackLayout

class TaskManagerApp(App):
    def build(self):
        self.tasks = StackLayout()  # Pour contenir les tâches
        self.scroll = ScrollView(do_scroll_x=False)
        self.scroll.add_widget(self.tasks)

        layout = BoxLayout(orientation='vertical')
        self.task_input = TextInput(hint_text='Entrez votre tâche ici')
        add_btn = Button(text='Ajouter', on_press=self.add_task)

        layout.add_widget(self.scroll)
        layout.add_widget(self.task_input)
        layout.add_widget(add_btn)

        return layout

    def add_task(self, instance):
        task_text = self.task_input.text
        if task_text:
            task_label = Label(text=task_text, size_hint_y=None, height=40)
            self.tasks.add_widget(task_label)
            self.task_input.text = ''  # Réinitialiser le champ de saisie

if __name__ == '__main__':
    TaskManagerApp().run()
```

### 3. Exécution de l'application
Pour exécuter votre application, ouvrez un terminal, naviguez vers le dossier de votre projet et lancez la commande suivante :
```bash
python main.py
```

### 4. Améliorations possibles
- **Suppression de tâches** : Ajouter un bouton pour supprimer les tâches.
- **Sauvegarde des tâches** : Implémenter un module pour sauvegarder les tâches dans un fichier.
- **Stylisation** : Ajouter des styles et améliorer l'interface utilisateur.

## Conclusion
Vous avez maintenant un gestionnaire de tâches simple construit avec Kivy. Explorez davantage les fonctionnalités de Kivy pour enrichir votre application.