# django_project_structure

1-Creation d'un environnement virtuel
python3 -m venv venv

2-Activation de l'environnement virtuel
source venv/bin/activate

3-Installation de Django
pip install django

4-Mise a jour de pip
pip install --upgrade pip

*Mise a jour des paquets installé:
pip freeze > requirements.txt

5-Creation d'un projet Django
django-admin startproject project_name

6-Naviguer vers le dossier du projet django
cd project_name

7-Creation d'une application django
django-admin startapp app_name

8-Configuration de notre application 

*Creer un fichier a la racine de notre application "app_name" crée et le nommé "urls.py"
*Se rendre dans le fichier "settings.py" du projet project_name
*Ajouter dans "INSTALLED_APP" le nom de notre application crée 
INSTALLED_APP  = [
    'app_name',
]
*Se rendre dans le fichier "urls.py" de notre projet crée et importer "include" :
from django.urls import include
*Ajouter ensuite cette ligne de code : 
    path('app_name/', include('app_name.urls')),

9-Mise en place de notre application 
Creer un dossier nommé "templates"
A l'interieur de ce dossier "templates" nous allons creer un sous dossier nommé "app_name"
A l'interieur de ce sous dossiers nous allons creer un fichier "home.html" qui va afficher "Bonjour ici c'est Django" grace a une balise HTML h1

*Se rendre dans le fichier views.py de notre application et creer une fonction

def home(request):
    return render(request,' app_name/home.html ')


*Ajouter ceci dans notre fichier "urls.py"
from .views import *

url_patterns = [
    path('home/', views.home, name='home' )
]

10-Demarrer le server
Rentrer la commande suivante pour demarrer notre server 
python3 manage.py runserver

Se rendre sur notre naviguateur et saisir l'url suivant 
127.0.0.0:8000/app_name/home

Et voila notre page affiche bien 
"Bonjour ici c'est Django"


