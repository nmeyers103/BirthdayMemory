# 1. Start from a Node 20+ base image
FROM node:20-alpine

# Set the working directory inside the container
WORKDIR /usr/src/app

# 2. Copy package.json/package-lock.json first for layer caching
COPY package*.json ./
RUN npm ci

# 3. Copy the rest of the client/ source code
COPY . .

# 4. Expose the default Vite port
EXPOSE 5173

# 5. Run Vite's dev server bound to all network interfaces (0.0.0.0)
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0"]
