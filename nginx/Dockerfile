# Gunakan image nginx resmi
FROM nginx:alpine

# Hapus default config bawaan nginx
RUN rm /etc/nginx/conf.d/default.conf

# Copy config kamu ke dalam container
COPY default.conf /etc/nginx/conf.d/default.conf

# (Opsional) tambahkan sertifikat SSL kalau nanti pakai HTTPS
# COPY ssl /etc/ssl/private/

# Expose port 80 untuk HTTP
EXPOSE 80

# Jalankan nginx (sudah default command di base image)
CMD ["nginx", "-g", "daemon off;"]
