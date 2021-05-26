FROM node:14-alpine

ENV NODE_ENV=${ENV}

#Editor nano para consola
RUN apk update && \
	apk add nano

# Crear directorio de trabajo
#RUN mkdir -p /opt/app

# Se estable el directorio de trabajo
WORKDIR /opt/app/

# Instala los paquetes existentes en el package.json
COPY ./package.json .
RUN npm init -y
RUN npm install 
RUN npm update

#COPY ${NODE_PROJECT_DIR} .
# Instalación de Nodemon en forma Global
# Al realizarse cambios reiniciar el servidor
RUN npm install nodemon -g 

# Expone la aplicación en el puerto configurado en el .env
EXPOSE 3000

# Inicia la aplicación al iniciar al contenedor
CMD nodemon -L --watch . app.js
