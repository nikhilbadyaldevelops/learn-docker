# Base image to copy from 
FROM node

# Working directory inside the container
WORKDIR /app

# Copying package json before so that npm install can be avoided
COPY package.json /app

# Command which we want to run when building image
RUN npm install

# Tells the docker, from where to copy from source and where to copy in dest
COPY . /app

# The port which will be exposed from container to our local machine
EXPOSE 80

# command to run in the container build from image
CMD ["node","server.js"]



