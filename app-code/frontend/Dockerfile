FROM nodejs:alpine AS build

WORKDIR /apps

COPY *.json .

RUN npm install

copy . .

RUN npm run build

FROM nodejs:alpine AS final

copy --from=build build .

EXPOSE 80

cmd ["npm", "start"]
