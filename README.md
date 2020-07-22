## demo app - developing with Docker

This demo app shows a simple user profile app set up using 
- index.html with pure js and css styles
- nodejs backend with express mode
- mongodb for data storage

All components are docker-based

#### To start the application

### Method 1 run by docker command
    docker build -t profile-app:1.0 .

    docker network create profile-app-network

    docker run \
    -d \
    --network profile-app-network \
    --name themongoserver \
    -p 27017:27017 \
    -e MONGO_INITDB_ROOT_USERNAME=admin \
    -e MONGO_INITDB_ROOT_PASSWORD=password \
    mongo
    

    docker run \
    -d \
    --network profile-app-network \
    --name theprofileapp \
    -p 3000:3000 \
    -e MONGODB_ADMINUSERNAME=admin \
    -e MONGODB_ADMINPASSWORD=password \
    -e MONGODB_SERVER=themongoserver \
    profile-app:1.0

### Method 2: start the app by docker-compose
    docker-compose build
    docker-compose up -d
## to stop the composed container
    docker-compose down -d
#### To test api-end point ####
    http://localhost:3000/get-profile
