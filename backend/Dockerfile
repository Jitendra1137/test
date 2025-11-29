FROM node:23-alpine
WORKDIR /app
COPY backend/package*.json ./
RUN npm ci --only=production
COPY backend/ .
EXPOSE 8000
CMD ["node", "server.js"]
