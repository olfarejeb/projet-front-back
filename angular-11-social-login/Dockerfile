#stage 1
FROM node:16.0.0 as node
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build --prod
#stage 2
FROM nginx:alpine
COPY --from=node /app/dist/Angular11SocialLogin /usr/share/nginx/html
 
EXPOSE 80
ENTRYPOINT ["nginx","-g","daemon off;"]

