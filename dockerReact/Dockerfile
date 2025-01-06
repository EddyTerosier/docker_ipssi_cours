FROM node:lts AS build

# Créer un répertoire de travail
WORKDIR /app

# Copier les fichiers de dépendances
COPY package.json package-lock.json ./

# Installer les dépendances
RUN npm install

# Copier les fichiers sources
COPY . .

# Build l'application = Générer le dossier build
RUN npm run build

# Étape NGINX
FROM nginx:latest

# Copier le dossier build dans le répertoire de travail de nginx
COPY --from=build /app/build /usr/share/nginx/html

# Exposer le port NGINX
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]