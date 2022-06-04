FROM node:18-alpine as builder

USER root

WORKDIR /app

COPY ./package.json ./

RUN npm i --fetch-timeout=3000000

COPY ./ ./

RUN ["npm","run","build"]

FROM nginx

EXPOSE 3000

COPY ./nginx/default.conf /etc/nginx/cong.d/default.conf

COPY --from=builder /app/build /usr/share/nginx/html