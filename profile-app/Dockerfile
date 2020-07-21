FROM node:13-alpine

EXPOSE 3000
ENV MONGO_DB_USERNAME=admin \
    MONGO_DB_PWD=password

RUN mkdir -p /home/app
WORKDIR /home/app
COPY . /home/app
RUN npm i

CMD ["node", "/home/app/server.js"]