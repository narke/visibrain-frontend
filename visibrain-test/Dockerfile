# Nodejs image
FROM node:18-alpine

# Working directory is /app
WORKDIR /app

# Copy the package.json and package-lock.json files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the code into the container
COPY . .

# Build the application
RUN npm run build

# Use an Nginx
FROM nginx:alpine

# Copy files from the previous stage
COPY --from=0 /app/dist /usr/share/nginx/html

# Expose nginx port 80
EXPOSE 80

