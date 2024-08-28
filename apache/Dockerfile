# Use an official Ubuntu as the base image
FROM ubuntu:latest

# Update the package list and install Apache and unzip
RUN apt-get update && apt-get install -y apache2 unzip

# Copy the todo.zip file from the local machine to the Docker image
COPY todo.zip /tmp/todo.zip

# Unzip the todo.zip file and move the contents to the Apache web root directory
RUN unzip /tmp/todo.zip -d /tmp && mv /tmp/*/* /var/www/html/

# Remove the default Apache index.html if still present
RUN rm -f /var/www/html/index.html

# Expose port 80 to the outside world
EXPOSE 80

# Start Apache when the container starts
CMD ["apache2ctl", "-D", "FOREGROUND"]
