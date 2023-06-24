FROM node:16-alpine AS build
WORKDIR /api
COPY . .
RUN npm install
RUN npm run build
CMD [ "node", "dist/main.js" ]
