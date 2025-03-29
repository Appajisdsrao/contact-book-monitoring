# Stage 1: Build the React App
FROM node:18-alpine AS builder

WORKDIR /app
COPY package.json package-lock.json ./


COPY . .
RUN npm run build
RUN npm install --force
RUN npm install --legacy-peer-deps

# Stage 2: Serve the React App with Nginx
FROM nginx:alpine
COPY --from=builder /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
