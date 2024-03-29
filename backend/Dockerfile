# Utilisez une image de base Node.js
FROM node:14

# Créez et définissez le répertoire de travail de l'application dans le conteneur
WORKDIR /usr/src/app

# Copiez le package.json et le package-lock.json dans le répertoire de travail
COPY package*.json ./

# Installez les dépendances de l'application
RUN npm install

# Copiez tous les fichiers de votre projet dans le répertoire de travail de l'application
COPY . .

# Exposez le port sur lequel l'application s'exécute
EXPOSE 5000

# Commande de démarrage de l'application
CMD ["npm", "start"]
