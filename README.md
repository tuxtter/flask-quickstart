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

```bash
python app.py
```

Se creara un socket en http://localhost:5000 donde podras visualizar la aplicacion.
