FROM node:23-alpine

WORKDIR /app

# Copy package files from backend folder
COPY package*.json ./

# Install deps
RUN npm ci --only=production

# Copy entire backend source
COPY . .

EXPOSE 8000

CMD ["node", "server.js"]
