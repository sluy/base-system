FROM node:14-alpine

ENV NODE_ENV=${ENV}

#Editor nano para consola
RUN apk update && \
	apk add nano

# Crear directorio de trabajo
#RUN mkdir -p /opt/app

# Se estable el directorio de trabajo
WORKDIR /opt/app/
# Expone la aplicación en el puerto adecuado
EXPOSE 3000

# Instalar loopback 4 cli
RUN npm i -g @loopback/cli
# Correr la app
RUN npm install 
# Correr el sistema (escuchando cambios)
CMD npm run start:watch