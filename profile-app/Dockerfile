#Choose the parent Image
FROM node:13-alpine 

# Specify the Port
EXPOSE 3000

# Make working directory for the app
RUN mkdir -p /home/app

# Specify the working directory for the app
WORKDIR /home/app

# Add the Code to the Container 
COPY . /home/app

# Install the dependencies
RUN npm i

# The entry point for the app
CMD ["node", "/home/app/server.js"]