FROM node:14.16.0-alpine as build

WORKDIR /src
COPY package.json package.json


RUN npm install

COPY . .

RUN npm run build

FROM nginx:1.8-alpine
COPY --from=build /src/dist /usr/share/nginx/html
