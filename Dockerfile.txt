# Use pre-built Apache + PHP image
FROM devopsedu/webapp

# Remove default application (optional cleanup)
RUN rm -rf /var/www/html/*

# Copy project files into container
COPY . /var/www/html/

# Expose Apache port
EXPOSE 80

# Start Apache in foreground
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
