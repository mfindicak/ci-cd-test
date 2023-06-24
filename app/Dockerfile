FROM node:16-alpine AS build
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

# Serve Application using Nginx Server
FROM nginx:alpine
COPY --from=build /app/dist/ci-cd-test/ /usr/share/nginx/html

# Reverse proxy configuration
RUN rm /etc/nginx/conf.d/default.conf
COPY nginx-reverse-proxy.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]