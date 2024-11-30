FROM node:18-alpine

WORKDIR /usr/app

COPY package*.json .

RUN npm install && npm install -g pm2  

COPY  . .

EXPOSE 5000

CMD ["pm2", "start", "server.js", "--name", "Zal-App-Backend", "--no-daemon"]
