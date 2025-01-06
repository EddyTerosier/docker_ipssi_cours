FROM python
LABEL authors="Eddyj"

# Définir le répertoire de travail
# Définit dans le conteneur le répertoire de travail et s'il n'existe pas, il le crée
WORKDIR /app

# Copier le fichier requirements.txt dans le répertoire de travail
COPY requirements.txt requirements.txt

# Installer les dépendances
RUN pip install --no-cache-dir -r requirements.txt

# Copier le contenu du répertoire courant dans le répertoire de travail
COPY .. .

# Commande à exécuter
CMD [ "python", "./app.py" ]