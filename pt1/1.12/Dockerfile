FROM node:lts-buster-slim

WORKDIR /usr/src/app

EXPOSE 5000

COPY . .

RUN npm install

RUN npm run build

RUN npm install -g serve

CMD [ "serve", "-s", "-l", "5000", "build"]