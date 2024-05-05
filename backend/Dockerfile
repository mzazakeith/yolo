FROM node:16.18.1-alpine
WORKDIR /usr/src/app/backend
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 5000
CMD [ "npm", "start" ]
