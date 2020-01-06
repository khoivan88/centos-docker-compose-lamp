# https://medium.com/@thivi/creating-a-lamp-stack-using-docker-compose-13ca4e3950e1

FROM httpd:2.4-alpine
RUN yum update; \
    yum upgrade;
# COPY ./httpd.conf /etc/httpd.conf

# Install useful tools and install important libaries
RUN yum -y update && \
    yum -y --no-install-recommends install curl wget unzip git vim \
openssl && \
    rm -rf /var/lib/apt/lists/* && \

EXPOSE 80
EXPOSE 443