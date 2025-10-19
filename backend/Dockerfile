# ============================
# STAGE 1: Build binary
# ============================
FROM golang:1.22-alpine AS builder

# Set working directory di dalam container
WORKDIR /app

# Copy go.mod dan go.sum untuk install dependency
COPY go.mod go.sum ./

# Download module (cached layer)


# Copy semua file ke container
COPY . .

# Build aplikasi jadi binary
RUN go build -o main .

# ============================
# STAGE 2: Run binary
# ============================
FROM alpine:latest

# Install timezone dan CA certificates biar HTTPS bisa jalan
RUN apk --no-cache add ca-certificates tzdata

# Set working directory di container
WORKDIR /root/

# Copy binary dari stage builder
COPY --from=builder /app/main .

# Expose port (ganti sesuai port app kamu)
EXPOSE 8080

# Jalankan aplikasi
CMD ["./main"]
