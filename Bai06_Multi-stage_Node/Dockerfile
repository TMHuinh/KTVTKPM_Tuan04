# =======================
# Stage 1: Build
# =======================
FROM node:18 AS build

# Thư mục làm việc
WORKDIR /app

# Copy package.json và package-lock.json trước để tận dụng cache
COPY package*.json ./

# Cài dependencies
RUN npm install

# Copy toàn bộ source code
COPY . .

# Build (nếu cần)
RUN npm run build

# =======================
# Stage 2: Run
# =======================
FROM node:18-alpine

WORKDIR /app

# Copy package.json & node_modules từ stage build
COPY --from=build /app/package*.json ./
COPY --from=build /app/node_modules ./node_modules

# Copy code đã build
COPY --from=build /app ./

# Chạy ứng dụng
CMD ["node", "index.js"]