FROM node:23-alpine

WORKDIR /app

COPY ../public/package*.json ./

RUN npm install

COPY ../public/ .

EXPOSE 5173

CMD ["npm", "run", "dev"]