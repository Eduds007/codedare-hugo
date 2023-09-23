+++
title = ' 🧨 Django ' 
subtitle = 'criando rotas com django'
date = 2023-09-22T15:50:16-03:00
draft = false
slug = '3'
image = "images/thumb3.png"
topic = ['Django', 'Python 🐍'] 
+++





## Introdução ao Django 🚀

Django é um framework Python de alto nível para o desenvolvimento rápido de aplicativos web. Ele é projetado para tornar o desenvolvimento web mais rápido e fácil, seguindo o princípio do "batteries-included" 🧰, o que significa que ele inclui muitos recursos úteis de fábrica. Neste tutorial, você aprenderá a configurar um ambiente de desenvolvimento Django e criar uma aplicação web básica.

### Pré-requisitos 📋

Certifique-se de ter o Python instalado em sua máquina. Você pode baixá-lo em [python.org](https://www.python.org/downloads/).

### Passo 1: Configurar um Ambiente Virtual 🛠️

É uma boa prática usar um ambiente virtual para isolar seu projeto Django. Abra o terminal e execute os seguintes comandos:

```bash
# Instale o pacote virtualenv 
pip install virtualenv

# Crie um ambiente virtual
virtualenv venv

# Ative o ambiente virtual
source venv/bin/activate   

# No Windows, use "venv\Scripts\activate"
```

### Passo 2: Instalar o Django 🌐

Dentro do ambiente virtual, você pode instalar o Django usando o pip:

```bash
pip install django
```

### Passo 3: Criar um Projeto Django 🎉

Para criar um novo projeto Django, execute o seguinte comando:

```bash
django-admin startproject myproject
```

Isso criará uma estrutura de diretórios para seu projeto.

### Passo 4: Criar uma Aplicação 📦

Dentro do diretório do projeto (onde você tem o arquivo `manage.py`), execute o seguinte comando para criar uma aplicação:

```bash
python manage.py startapp myapp
```

Isso criará a estrutura de diretórios para sua aplicação.

### Passo 5: Configurar o Banco de Dados 🗃️

Edite o arquivo `myproject/settings.py` e configure o banco de dados. Você pode usar o banco de dados SQLite padrão para começar:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 
        'db.sqlite3'),
    }
}
```

### Passo 6: Criar um Modelo 📊

Em `myapp/models.py`, crie um modelo de dados simples:

```python
from django.db import models

class Item(models.Model):
    name = models.CharField(max_length=100)

    def __str__(self):
        return self.name
```

### Passo 7: Criar uma Visualização 👀

Em `myapp/views.py`, crie uma visualização simples:

```python
from django.shortcuts import render
from .models import Item

def item_list(request):
    items = Item.objects.all()
    return render(request, 
    'myapp/item_list.html'
    , {'items': items})
```

### Passo 8: Criar uma Página HTML 📝

Crie um arquivo HTML em `myapp/templates/myapp/item_list.html`:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Lista de Itens</title>
</head>
<body>
    <h1>Lista de Itens</h1>
    <ul>
        {% for item in items %}
            <li>{{ item.name }}</li>
        {% endfor %}
    </ul>
</body>
</html>
```

### Passo 9: Configurar URLs 🌐

Em `myapp/urls.py`, crie uma URL para a visualização:

```python
from django.urls import path
from . import views

urlpatterns = [
    path('items/', views.item_list,
     name='item_list'),
]
```

Em `myproject/urls.py`, inclua as URLs da aplicação:

```python
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('myapp.urls')),
]
```

### Passo 10: Aplicar Migrações 🚚

Aplique as migrações para criar o banco de dados:

```bash
python manage.py makemigrations
python manage.py migrate
```

### Passo 11: Iniciar o Servidor 🚀

Inicie o servidor Django:

```bash
python manage.py runserver
```

Você verá uma saída indicando que o servidor está ativo e ouvindo em `http://127.0.0.1:8000/`.

### Passo 12: Acessar a Aplicação 🌍

Abra seu navegador da web e acesse `http://127.0.0.1:8000/items/`. Você deverá ver a lista de itens criada a partir do modelo de dados.

## Conclusão 🎉

Você criou uma aplicação web simples usando o framework Django! Este é apenas o começo, e o Django oferece muitos recursos poderosos para criar aplicativos web mais complexos. Continue aprendendo e explorando para criar aplicativos web personalizados com Python e Django.

Para informações mais detalhadas, consulte a [documentação oficial do Django](https://docs.djangoproject.com/en/3.2/).

Aproveite seu aprendizado com o Django! 😄👍