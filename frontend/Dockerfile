# Supported Node.js LTS base image
FROM node:20-alpine

# Working directory inside the container
WORKDIR /app

# Copy package files first so the dependency layer is cached
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the frontend source code
COPY . .

# Next.js embeds NEXT_PUBLIC_* values at build time
ARG NEXT_PUBLIC_API_URL
ENV NEXT_PUBLIC_API_URL=$NEXT_PUBLIC_API_URL

# Create the production build
RUN npm run build

# Frontend port
EXPOSE 3000

# Start Next.js in production mode
CMD ["npm", "start"]
