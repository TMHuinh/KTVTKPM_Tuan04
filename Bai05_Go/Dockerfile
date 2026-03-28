# Stage 1: Build Go app
FROM golang:1.20 AS build

WORKDIR /app
COPY main.go .
RUN go build -o app main.go

# Stage 2: Run binary
FROM alpine:latest
WORKDIR /app
COPY --from=build /app/app .
CMD ["./app"]