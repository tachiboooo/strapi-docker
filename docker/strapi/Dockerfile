FROM node:18.12.1-alpine3.15
# Installing libvips-dev for sharp Compatibility
RUN apk update && apk add --no-cache build-base gcc autoconf automake zlib-dev libpng-dev nasm bash vips-dev
ARG NODE_ENV=production
ENV NODE_ENV=${NODE_ENV}

WORKDIR /opt/
COPY ./app/package.json ./app/package-lock.json ./
RUN npm config set fetch-retry-maxtimeout 600000 -g && npm install
ENV PATH /opt/node_modules/.bin:$PATH

WORKDIR /opt/app
COPY ./app ./

RUN chmod -R 777 /opt/app
USER node
RUN npm run build

EXPOSE 1337
CMD ["npm", "start"]