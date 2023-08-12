# syntax=docker/dockerfile:1

#La version de la imagen
FROM python:3.7-alpine

# El directorio en donde va estar la app
WORKDIR /code

# variables de entorno
## El archivo que va ejecutar
ENV FLASK_APP=app.py
## IP interna 
ENV FLASK_RUN_HOST=0.0.0.0

# Modulos de python
RUN apk add --no-cache gcc musl-dev linux-headers

# Leer y copiar
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

# Copiar todo el codigo dentro del contenedor
COPY . .

CMD ["flask", "run"]

# EXPOSE 5000