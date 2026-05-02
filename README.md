# flask-quickstart

Pasos para crear app con Flask y Tailwind

## Parte 1 (branch parte1)

## Preparar el ambiente virtual

```bash
mkdir tailwind_flask_tutorial
cd tailwind_flask_tutorial
python -m venv tailwind-flask-venv
#tailwind-flask-venv\Scripts\Activate.ps1
source tailwind-flask-venv\bin\activate
pip install flask 
#$env:FLASK_ENV='development'
export FLASK_ENV='development'
```
## Integrar template y agregar estilo usando Tailwind

Crear el archivo app.py

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello World'

if __name__ == '__main__':
    app.run(debug=True)
```

Iniciar la aplicación

```bash
python app.py
```

Se creara un socket en http://localhost:5000 donde podras visualizar la aplicacion.

## Parte 2 (branch parte2)

## Agregar los folders para almacenar templates y estilos

```bash
mkdir -p templates static/css
```

Crear el template en templates/index.html:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h2>Hello World Medium</h2>
</body>
</html>
```

Crear el archivo de estilos para incluir tailwind

```css
@import "tailwindcss";
```

Agregar el template al archivo app.py

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def hello_world():
    return render_template('index.html')

if __name__ == '__main__':
    app.run(debug=True)
```

Iniciar la aplicación

```bash
python app.py
```

Verificar en http://localhost:5000

## Parte 3 (branch parte3)

Instalar Tailwind

```bash
npm install tailwindcss @tailwindcss/cli
npx @tailwindcss/cli -i ./static/css/style.css -o ./static/css/output-style.css --watch
```

Si alguno de estos pasos falla, prueba instalando la ultima version de nodejs y si estas en Windows, instala tambien Microsoft Visual C++ Redistributable.

Ahora agregar el output-style.css al template en templates/index.html.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="{{url_for('static', filename='css/output-style.css')}}">
    <title>Document</title>
</head>
<body>
    <h2 class='text-4xl text-center font-mono py-5 font-black text-emerald-600'>Hello World Medium</h2>
</body>
</html>
```

Iniciar la aplicación

```bash
python app.py
```

Verificar en http://localhost:5000

