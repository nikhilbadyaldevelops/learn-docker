FROM node:17-alpine


WORKDIR /app

COPY package.json .

RUN npm install 

COPY . . 


ARG DEFAULT_PORT

ENV PORT $DEFAULT_PORT

EXPOSE $PORT

# VOLUME [ "/app/feedback" ]


CMD ["npm","start"]