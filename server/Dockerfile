# Use Node 18 as base
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm ci

# Copy all source code
COPY . .

# Generate Prisma client
RUN npx prisma generate

# Build TypeScript
RUN npm run build

# Expose port (optional, e.g., 3000)
EXPOSE 3000

# Start the app
CMD ["node", "dist/index.js"]
