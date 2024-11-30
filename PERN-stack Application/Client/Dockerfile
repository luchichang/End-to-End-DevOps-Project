# Base image fo level1
FROM node:18-alpine AS build

# setting up the working directory
WORKDIR /usr/app

ENV Backend_Base_Url=http://backend:5000  

COPY package*.json .

RUN npm install 

COPY . .

RUN npm run build

# stage 2
FROM nginx:alpine 

ENV Backend_Base_Url=http://backend:5000  

COPY  --from=build /usr/app/build/  /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]



