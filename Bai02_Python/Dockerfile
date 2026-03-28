# Base image Python 3.9
FROM python:3.9

# Thư mục làm việc
WORKDIR /app

# Copy file requirements và cài đặt dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy source code
COPY app.py .

# Expose cổng 5000
EXPOSE 5000

# Chạy ứng dụng
CMD ["python", "app.py"]