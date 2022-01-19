FROM node:17-alpine

WORKDIR /app

COPY package.json .

RUN npm install 

COPY . .

EXPOSE 80

ENV MONGO_USERNAM=root
ENV MONGO_PASSWORD=root

CMD ["npm","start"]