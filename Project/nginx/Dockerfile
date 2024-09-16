# Use the official Nginx image
FROM nginx:alpine

# Copy Nginx configuration file
COPY nginx.conf /etc/nginx/nginx.conf

# Create directory for SSL certificates
RUN mkdir -p /etc/nginx/certs

# Copy SSL certificates
COPY certs/server.crt /etc/nginx/certs/server.crt
COPY certs/server.key /etc/nginx/certs/server.key

# Expose ports 80 and 443
EXPOSE 80 443
