#stage 1
FROM node:16-alpine as node
WORKDIR /app
COPY . .
RUN npm ci
RUN npm run build --prod
#stage 2
FROM nginx:alpine
COPY --from=node /app/dist/client /usr/share/nginx/html
EXPOSE 80