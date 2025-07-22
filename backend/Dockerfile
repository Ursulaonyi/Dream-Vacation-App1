# Use Node.js 18 LTS as base image
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Set environment variables (optional for Dockerfile)
ENV PORT=3001

# Expose port
EXPOSE 3001

# Start the backend server
CMD ["npm", "start"]
