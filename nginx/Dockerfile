FROM nginx:1.25.2-alpine
LABEL version="1.0.0" description="Nginx container for 2025cloud project"
COPY index.html /usr/share/nginx/html/index.html

# Add a health check
HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
  CMD curl -f http://localhost/ || exit 1
