FROM ubuntu:xenial

ENV API_UMBRELLA_VERSION 0.14.4-1~xenial

# Install API Umbrella
RUN apt-get update && apt-get -y install wget
RUN apt-get -y install wget libffi6 libyaml-0-2 logrotate curl libxml2 tcl openjdk-8-jre-headless libcurl3 psmisc perl
RUN wget https://github.com/martel-innovate/api-umbrella/releases/download/v0.14.4-fiware/api-umbrella_0.14.4-1.xenial_amd64.deb
RUN dpkg -i api-umbrella_0.14.4-1.xenial_amd64.deb
RUN apt-get -y -f install


# Define mountable directories
VOLUME ["/etc/api-umbrella", "/opt/api-umbrella/var/db", "/opt/api-umbrella/var/log"]

# Expose HTTP and HTTPS ports
EXPOSE 80 443

# Run the API Umbrella service
CMD ["api-umbrella", "run"]
