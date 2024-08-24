FROM node:14 AS build

WORKDIR /apps

COPY *.json ./

RUN npm install

COPY . .

RUN npm run build

FROM node:14-alpine AS final

WORKDIR /apps

COPY --from=build /apps/build .

EXPOSE 80

CMD ["npm", "start"]
