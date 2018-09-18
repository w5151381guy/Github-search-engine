FROM node:10-alpine AS build

WORKDIR /app

ADD package.json /app/
RUN npm install yarn -g
RUN yarn 

ADD ./server/index.js /app/
CMD node index.js