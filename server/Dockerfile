WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN npm ci

# Copy source code
COPY . .

# Generate Prisma client in source folder
RUN npx prisma generate

# Build TypeScript
RUN npm run build

# Start app
CMD ["node", "dist/index.js"]
