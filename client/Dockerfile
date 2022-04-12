# step 1 - build static files
FROM node:16-alpine as build-step

WORKDIR /app

ENV PATH /app/node_modules/.bin:$PATH

COPY client/package.json client/babel.config.js ./
COPY client/src ./src
COPY client/public ./public

RUN npm install
RUN npm run build

# step 2 - nginx

FROM nginx:stable-alpine

COPY --from=build-step /app/dist /usr/share/nginx/html
COPY deployment/nginx.default.conf /etc/nginx/conf.d/default.conf
