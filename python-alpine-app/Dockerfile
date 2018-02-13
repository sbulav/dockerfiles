############################################################
# Dockerfile to build Python WSGI Application Containers
# Based on Alpine
############################################################
# Using python2.7 alpine image
FROM python:2.7.14-alpine 
MAINTAINER Bulavintsev Sergey
ENV version 0.0.2
ENV http_proxy http://10.10.119.11:3128
ENV https_proxy https://10.10.119.11:3128

# Copy application to apache cgi-bin
ADD application/ /var/www/localhost/cgi-bin/

# Update image and install apache
RUN apk update &&      \
apk upgrade &&         \ 
apk add apache2 &&     \
mkdir /run/apache2 &&  \
chmod 755 /var/www/localhost/cgi-bin/*.py && \
#Uncommend cgi-bin
sed -i 's/#LoadModule cgi_module/LoadModule cgi_module/' /etc/apache2/httpd.conf && \
sed -i 's/#AddHandler cgi-script .cgi/AddHandler cgi-script .py/' /etc/apache2/httpd.conf && \
sed -i 's/Options none/Options ExecCGI/' /etc/apache2/httpd.conf

# Expose ports
EXPOSE 80

# Set the default directory where CMD will execute
#CMD [/bin/mkdir, /run/apache2, ;, /usr/sbin/httpd, -D, FOREGROUND]

# Start httpd
ENTRYPOINT ["/usr/sbin/httpd"]
CMD ["-D", "FOREGROUND"]
