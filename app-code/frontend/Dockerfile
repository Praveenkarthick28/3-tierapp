FROM node:14 AS build

WORKDIR /apps

COPY *.json ./

RUN npm install

copy . .

EXPOSE 80

cmd ["npm", "start"]
