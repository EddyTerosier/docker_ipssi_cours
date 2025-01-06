FROM node:lts AS build

# Crée un répertoire de travail
WORKDIR /app

# Copie les fichiers de dépendances
COPY package.json package-lock.json ./

# Installe les dépendances
RUN npm install

# Copie les fichiers sources
COPY . .

# Build l'application = Génère le dossier build
RUN npm run build

# Étape NGINX
FROM nginx:latest

# Copie le dossier build dans le répertoire de travail de nginx
COPY --from=build /app/build /usr/share/nginx/html

# Expose le port NGINX
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]