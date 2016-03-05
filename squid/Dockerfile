FROM debian:jessie
RUN apt-get -q update && apt-get -qy install python squid3 wget telnet vim
RUN sed -i "s/^#http_access deny all/http_access allow all/" /etc/squid3/squid.conf
RUN sed -i "s/^#http_access allow localnet/http_access allow all/" /etc/squid3/squid.conf
RUN mkdir -p /var/cache/squid3
RUN chown -R proxy:proxy /var/cache/squid3
ADD deploy_squid.py /tmp/deploy_squid.py
CMD /tmp/deploy_squid.py
