# ========================
# Stage 1: Build React app
# ========================
FROM node:18-alpine AS build

# Thư mục làm việc
WORKDIR /app

# Copy package.json và package-lock.json
COPY package*.json ./

# Cài dependencies
RUN npm install

# Copy toàn bộ source code
COPY . .

# Build app
RUN npm run build

# ========================
# Stage 2: Serve production build
# ========================
FROM nginx:alpine

# Copy build từ stage trước sang nginx html folder
COPY --from=build /app/build /usr/share/nginx/html

# Expose cổng 80
EXPOSE 80

# Chạy nginx
CMD ["nginx", "-g", "daemon off;"]