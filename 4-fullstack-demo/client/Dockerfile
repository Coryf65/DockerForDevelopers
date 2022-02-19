# Client Dockerfile
# get an image of node from Dockerhub
FROM node

# app working directory
WORKDIR /client

# copy this into the client folder
COPY package*.json /client

# install all dependencies
RUN npm install

# copy everything into the client folder
COPY . /client/

EXPOSE 3000

# run a bash command
CMD [ "npm", "start" ]