FROM node:lts

# Créer un répertoire de travail
WORKDIR /app

# Copier les fichiers de dépendances
COPY package.json .

# Installer les dépendances
RUN npm install

# Copier les fichiers sources
COPY . .

# Exposer le port 8080
EXPOSE 8080

# Lancer l'application
CMD ["npm", "run", "dev"]