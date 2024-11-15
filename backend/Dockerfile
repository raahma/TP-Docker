# Utiliser une image Python
FROM python:3.9-slim

# Définir le répertoire de travail
WORKDIR /app

# Copier le fichier requirements.txt et installer les dépendances
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# Copier tout le contenu du backend
COPY . .

# Exposer le port 5000
EXPOSE 5000

ENV FLASK_APP=application.py

# Lancer l'application Flask avec le bon module
CMD ["flask", "run", "--host=0.0.0.0"]
