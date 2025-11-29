# Stage 1: Build React (Vite)
FROM node:23-alpine AS build

WORKDIR /app

# Copy package files
COPY package*.json ./

# Install deps
RUN npm install

# Copy rest of frontend source code
COPY . .

# Build app
RUN npm run build

# Stage 2: Nginx serve
FROM nginx:stable-alpine

COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
