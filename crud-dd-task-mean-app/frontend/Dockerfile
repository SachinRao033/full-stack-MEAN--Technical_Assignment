# Stage 1 - Build Angular

FROM node:18-alpine as build
WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

RUN npm run build --configuration production


# Stage 2 - Serve with Nginx

FROM nginx:alpine
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html


COPY nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
