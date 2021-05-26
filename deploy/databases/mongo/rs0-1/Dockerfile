FROM mongo:4.4.6

# Workdir configs directory
WORKDIR /usr/src/configs

# Copy config files
COPY mongo.conf .

EXPOSE 27017

CMD ["--config", "./mongo.conf"]

RUN echo "Configurando dependencias ..."
RUN apt-get update
RUN apt install nano -y
RUN apt install python-minimal -y
RUN apt install python-pymongo -y
RUN apt install wget -y
RUN wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | apt-key add -
RUN echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.4 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-4.4.list
RUN apt update -y
RUN apt install mongocli -y
