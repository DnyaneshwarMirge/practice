# Use an official Ubuntu as the base image
FROM ubuntu:latest

# Update the package list and install Apache and unzip
RUN apt-get update && apt-get install -y apache2 unzip wget

# Download the Oxer template zip file
RUN wget https://www.free-css.com/assets/files/free-css-templates/download/page296/oxer.zip -O /tmp/oxer.zip

# Unzip the template into the Apache web root directory
RUN unzip /tmp/oxer.zip -d /tmp && mv /tmp/Oxer/* /var/www/html/

# Remove the default Apache index.html if still present
RUN rm -f /var/www/html/index.html

# Expose port 80 to the outside world
EXPOSE 80

# Start Apache when the container starts
CMD ["apache2ctl", "-D", "FOREGROUND"]
