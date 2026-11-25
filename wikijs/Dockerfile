
# Image de base contenant Node.js
FROM node:24-bookworm

# Dossier de travail
WORKDIR /wiki

# Installation des outils necessaires
RUN apt-get update && apt-get install -y wget \
    && rm -rf /var/lib/apt/lists/*

# Telechargement et extraction de Wiki.js
RUN wget https://github.com/Requarks/wiki-v2/releases/download/v2.5.317/wiki-js.tar.gz \
    && tar -xzf wiki-js.tar.gz \
    && rm wiki-js.tar.gz

# Copie du fichier de configuration
COPY config.yml /wiki/config.yml

RUN chown -R node:node /wiki
USER node

# Port utilise par Wiki.js
EXPOSE 3000

# Demarrage de l'application
CMD ["node", "server"]

