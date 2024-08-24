FROM node:14 AS build

WORKDIR /apps

COPY *.json ./

RUN npm install

copy . .

RUN npm run build

FROM node:14-alpine AS final

WORKDIR /apps

copy --from=build /apps/build .

EXPOSE 80

cmd ["npm", "start"]
