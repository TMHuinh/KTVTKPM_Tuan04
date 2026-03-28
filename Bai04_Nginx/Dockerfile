# Dùng base image Nginx chính thức
FROM nginx:latest

# Copy file index.html vào thư mục serve của nginx
COPY index.html /usr/share/nginx/html/index.html

# Expose cổng 80
EXPOSE 80

# Chạy nginx
CMD ["nginx", "-g", "daemon off;"]