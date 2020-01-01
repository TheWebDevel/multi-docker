#Base Image
FROM node:alpine

#Workdir
WORKDIR /app

#Copy package.json to Workdir
COPY ./packege*.json ./

# Install Dependencies
RUN npm install

#Copy Project to Workdir
COPY . .

# Run Application
CMD [ "npm", "run", "start" ]