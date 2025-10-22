# Use a small, modern Node.js image
FROM node:20-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy only package files first (for better layer caching)
COPY package*.json ./

# Install dependencies (no dev dependencies for production)
RUN npm install --omit=dev

# Copy the rest of the project files
COPY . .

# Expose the port (matches your server.js PORT)
EXPOSE 8080

# Default command to start the gateway
CMD ["npm", "start"]
