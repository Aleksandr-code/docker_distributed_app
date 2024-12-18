FROM node:20-alpine as base

WORKDIR /var/www/app/frontend

COPY ../package*.json /var/www/app/frontend/

RUN npm install

COPY ../ .

FROM base AS dev

EXPOSE 80

CMD ["npm", "run", "dev"]

FROM base AS build

RUN npm run build

FROM nginx:1.27-alpine as prod

COPY _docker/nginx/nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=build /var/www/app/frontend/dist /usr/share/nginx/html

EXPOSE 80

CMD [ "nginx", "-g", "daemon off;" ]