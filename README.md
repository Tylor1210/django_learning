1. python -m django --version

2. python3 -m venv .venv

3. source.venv/bin/activate
-deactivate (& enter in terminal to deactivate)
4. pip install django (now that venv is activated)
5. django-admin --version to check version

start server
python to get to % terminal 
cd to your project folder terminal
do python3 manage.py runserver (port) if you dont put port default is 8000

go to localhost:8000 and it should show success page


add your pages 
in urls.py in the url patterns [] add
path('', ), (home page)
path('about/',), (about page)

create a views.py file
and import django
from fjango.http import http


TEMPLATE DIRECTORIES
create a templates folder
create html templates 
settings.py line 57 ish DIRS ARRAY add 


EDIT views.py file to look something like this
#from django.http import HttpResponse
from django.shortcuts import render
def homepage(request):
    #return HttpResponse("Hello World! Im home")
    return render(request, 'home.html')
def about(request):
    #return HttpResponse("My about page.")
    return render(request, 'about.html')

############################################################

CSS

Create static folder
create css folder inside static
create css file inside css folder

basic css 
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    min-height: 100vh;
    display: grid;
    place-content: center;
    font-size: 3rem;
    background-color: black;
    color: whitesmoke;
}

h1, p {
    text-align: center;
}


go to settings.py
tell django where our static file is 
in settings.py line 12 add 
import os
then line 120 under STATIC_URLS add
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'static')
]

LINK STATIC CSS to HTML 
in home.html and all other html add 
{% load static %} on line 2 
and under title (line 8)
# <link rel="stylesheet" href="{% static 'css/style.css' %}">

LINK STATIC JS TO HTML
in static add js folder 
in js folder add main.js file
add <script src="{% static 'js/main.js' %}" defer></script> (line 8)

