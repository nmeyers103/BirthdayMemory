# 1. Start from a Node 20+ base image
FROM node:20-alpine

# Set the working directory inside the container
WORKDIR /usr/src/app

# 2. Copy package.json/package-lock.json first and run npm ci for better layer caching
COPY package*.json ./
RUN npm ci

# 3. Copy the rest of the server/ source code
COPY . .

# 4. Expose the API port
EXPOSE 4000

# 5. Run the app with its existing start script from server/package.json
CMD ["npm", "start"]
