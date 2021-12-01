# Create image from the Docker Hub
# https://hub.docker.com/_/node
FROM node:16

# Create app directory
WORKDIR /app

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json .

RUN npm install
# If you are building your code for production
# RUN npm ci --only=production

# Bundle (copy) app source
COPY . /app

# Your app binds to port 3000 so you'll use the EXPOSE instruction to have it mapped by the docker daemon:
EXPOSE 3000

# Last but not least, define the command to run your app using CMD which defines your runtime. Here we will use node server.js to start your server:
# CMD [ "node", "server.js" ]
CMD ["npm" ,"start" ]
