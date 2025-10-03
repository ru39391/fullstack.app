FROM node:23-alpine

WORKDIR /app

COPY ../public/package*.json .

RUN npm install

COPY ../public/ .

CMD ["npm", "run", "dev"]