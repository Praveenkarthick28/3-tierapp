FROM node:14-alpine AS build
# using lightweight image for build

WORKDIR /usr/src/app

COPY package*.json ./

# RUN apt install npm --no-install-recommends
#  --no-install-recommends flag  to avoid installing recommends

# Remove any temporary files or caches
RUN npm install && npm cache clean --force

COPY . .

# using lightweight image as final image
FROM node:14-alpine AS final

WORKDIR /usr/local/app

#copying build files from build image to final
COPY --from=build /usr/src/app /usr/local/app

CMD ["npm", "start"]
