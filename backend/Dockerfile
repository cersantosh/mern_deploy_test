# Base image: Node.js on lightweight Alpine Linux
FROM node:18-alpine

# Set working directory in container
WORKDIR /app

# Copy dependency files first (for caching)
COPY package*.json ./

# Install only production dependencies
RUN npm install --production

# Copy backend source code
COPY . .

# Expose the port backend listens on
EXPOSE 8000

# Start backend
CMD ["node", "index.js"]
