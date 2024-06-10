# Usa una imagen oficial de Python como imagen base
FROM python:3.9-slim

# Establece el directorio de trabajo en /app
WORKDIR /app

# Copia el archivo de requisitos y el código del proyecto
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

COPY . .

# Copiar el archivo .env
COPY .env .env

# Exponer el puerto en el que la aplicación Django correrá
EXPOSE 8000

# Comando para correr la aplicación Django
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "portfolio.wsgi:application"]
