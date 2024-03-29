# Utilisez une image de base Node.js avec l'environnement de production
FROM node:14 as build

# Créez et définissez le répertoire de travail de l'application dans le conteneur
WORKDIR /usr/src/app

# Copiez le package.json et le package-lock.json dans le répertoire de travail
COPY package*.json ./

# Installez les dépendances de l'application
RUN npm install

# Copiez tous les fichiers de votre projet dans le répertoire de travail de l'application
COPY . .

# Construisez l'application React pour la production
RUN npm run build

# Utilisez une image de base nginx pour servir l'application
FROM nginx:latest

# Copiez les fichiers de build de l'application React dans le répertoire de travail de nginx
COPY --from=build /usr/src/app/build /usr/share/nginx/html

# Exposez le port 80 sur lequel nginx s'exécute
EXPOSE 80

# Aucune commande de démarrage n'est nécessaire car nginx démarre automatiquement
