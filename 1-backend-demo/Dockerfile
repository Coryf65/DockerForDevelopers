FROM node 

# setting our working directory
WORKDIR /usr/src/app

COPY package*.json ./

# install dependencies
RUN npm install

# copy directory from local to the container
COPY . .

# allow needed ports
EXPOSE 4000

# run the app
CMD [ "npm", "start" ]