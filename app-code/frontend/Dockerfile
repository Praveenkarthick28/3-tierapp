FROM node:14 AS build

WORKDIR /apps

COPY *.json ./

RUN npm install

FROM node:14-alpine AS final

WORKDIR /apps

COPY --from=build /apps .

COPY . .

EXPOSE 80

CMD ["npm", "start"]
