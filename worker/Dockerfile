FROM node:18-alpine

USER root

WORKDIR /app

COPY ./package.json ./

RUN npm i --fetch-timeout=3000000

COPY ./ ./

CMD [ "npm","run","start" ]
