+++
title = '🌶️ Flask '
subtitle = 'Começando a programar Backend'
date = 2023-09-22T15:50:16-03:00
draft = false
slug = '2'
image = "images/thumb2.png"
topic = ['Flask', 'Backend'] 
+++



## Introdução ao Flask 🚀

O Flask é um microframework da web para Python que facilita a criação de aplicativos web simples e poderosos. Neste tutorial, você aprenderá a configurar um ambiente de desenvolvimento Flask e criar uma aplicação web básica.

### Pré-requisitos 📋

Certifique-se de ter o Python instalado em sua máquina. Você pode baixá-lo em [python.org](https://www.python.org/downloads/).

### Passo 1: Configurar um Ambiente Virtual 🍀

É uma prática recomendada usar um ambiente virtual para isolar seu projeto Flask. Abra o terminal e execute os seguintes comandos:

```bash
# Instale o pacote virtualenv 
pip install virtualenv

# Crie um ambiente virtual
virtualenv venv

# Ative o ambiente virtual
source venv/bin/activate   
# No Windows, use "venv\Scripts\activate"
```

### Passo 2: Instalar o Flask 🌶️

Dentro do ambiente virtual, você pode instalar o Flask usando o pip:

```bash
pip install Flask
```

### Passo 3: Criar um Aplicativo Flask Simples 🌐

Crie um arquivo chamado `app.py` e adicione o seguinte código:

```python
from flask import Flask

# Crie uma instância do Flask
app = Flask(__name__)

# Defina uma rota e a função associada
@app.route('/')
def hello_world():
    return 'Olá, Flask! 🌶️'

# Executar o aplicativo se este arquivo
# for o ponto de entrada
if __name__ == '__main__':
    app.run()
```

### Passo 4: Executar a Aplicação 🚀

No terminal, execute o aplicativo Flask digitando o seguinte comando:

```bash
python app.py
```

Isso iniciará o servidor Flask. Você verá uma saída indicando que o servidor está ativo e ouvindo em `http://127.0.0.1:5000/`.

### Passo 5: Acessar a Aplicação 🌐

Abra seu navegador da web e acesse `http://127.0.0.1:5000/`. Você deverá ver a mensagem "Olá, Flask! 🌶️" exibida na página.

## Conclusão 🎉

Você acabou de criar uma aplicação web simples usando o Flask! Este é apenas o começo, e o Flask oferece muitos recursos poderosos para construir aplicativos web mais complexos. Continue aprendendo e explorando para criar aplicativos web personalizados com Python e Flask.

Para informações mais detalhadas, consulte a [documentação oficial do Flask](https://flask.palletsprojects.com/en/2.1.x/).

Aproveite seu aprendizado com Flask! 😄👍