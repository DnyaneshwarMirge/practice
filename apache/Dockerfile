FROM ubuntu:latest

RUN apt-get update && apt-get install -y apache2 unzip wget

# Download and verify the zip file
RUN wget https://www.free-css.com/assets/files/free-css-templates/download/page296/oxer.zip -O /tmp/oxer.zip && \
    unzip -l /tmp/oxer.zip

# Unzip the file and move the contents to the Apache web root
RUN unzip /tmp/oxer.zip -d /tmp && mv /tmp/*/* /var/www/html/

RUN rm -f /var/www/html/index.html

EXPOSE 80

CMD ["apache2ctl", "-D", "FOREGROUND"]
