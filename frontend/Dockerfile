FROM node:14

WORKDIR /app

COPY . /app

ENV VITE_BACKEND_URI=/api

RUN npm install

RUN npm run build

EXPOSE 5000

CMD [ "npm", "run", "serve" ]