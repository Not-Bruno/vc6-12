FROM ubuntu:22.04

# Install Squid
RUN apt-get update && apt-get install -y squid && apt-get clean

# Copy Squid configuration
COPY squid.conf /etc/squid/squid.conf

# Expose Squid's default port
EXPOSE 3128

# Start Squid in foreground mode
CMD ["squid", "-N", "-f", "/etc/squid/squid.conf"]