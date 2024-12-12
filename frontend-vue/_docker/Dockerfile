FROM node:20-alpine as build-stage

WORKDIR /var/www/app/frontend

COPY ../package*.json /var/www/app/frontend/

RUN npm install



COPY ../ .

RUN npm run build

FROM nginx:1.27 as production-stage

COPY _docker/nginx/nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=build-stage /var/www/app/frontend/dist /usr/share/nginx/html

EXPOSE 3000

CMD [ "nginx", "-g", "daemon off;" ]