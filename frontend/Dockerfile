# Stage 1: Build frontend
FROM node:18-alpine AS build

WORKDIR /app

COPY package*.json ./
RUN npm install --production

COPY . .
RUN npm run build

# Stage 2: Serve with Nginx
FROM nginx:alpine

# Copy build output from stage 1
COPY --from=build /app/dist /usr/share/nginx/html

# Expose HTTP port
EXPOSE 80

# Keep Nginx in foreground
CMD ["nginx", "-g", "daemon off;"]
