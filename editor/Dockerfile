# Use Node.js 20 LTS (small Alpine image)
FROM node:20-alpine

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json first
COPY package*.json ./

# Install production dependencies
RUN npm install --only=production

# Copy the rest of the app
COPY . .

# Environment variables
ENV NODE_ENV=production
ENV TOKEN_SECRET_KEY=change_this_secret
ENV PORT=8080

# Expose Koyeb's expected port
EXPOSE 8080

# Start Manifest in production mode
CMD ["npm", "run", "start:prod"]
