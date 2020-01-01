# Builder Phase
# Base Image
FROM node:alpine as builder

# Set Workdir
WORKDIR /app

# Copy package.json files inside Workdir
COPY ./packege*.json .

# Install Dependencies
RUN npm install

# Copy the Rest of the Dir to Workdir
COPY . .

# Build Project
RUN npm run build


# Final Phase
# Base Image
FROM nginx

# Expose Port 3000
EXPOSE 3000

# Copy nginx config inside Image
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

# Copy Build files from Builder Phase to Final Phase
COPY --from=builder /app/build /usr/share/nginx/html