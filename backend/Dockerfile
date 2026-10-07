# Supported Node.js LTS base image
FROM node:20-alpine

# Working directory inside the container
WORKDIR /app

# Copy package files first so the dependency layer is cached
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the backend source code
COPY . .

# Backend API port
EXPOSE 3001

# Start the backend (the repo has no start script)
CMD ["node", "src/server.js"]
