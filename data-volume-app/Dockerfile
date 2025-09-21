FROM node:latest

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

ENV PORT 80

EXPOSE $PORT

# VOLUME [ "/app/node_modules" ]

CMD [ "npm", "start" ]