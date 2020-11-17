FROM httpd:2.4


RUN apt update 
RUN apt install curl apt-utils -y
RUN curl -L -k -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.6.1-amd64.deb
RUN dpkg -i filebeat-7.6.1-amd64.deb
RUN curl -L -k -O https://artifacts.elastic.co/downloads/beats/metricbeat/metricbeat-7.6.1-amd64.deb
RUN dpkg -i metricbeat-7.6.1-amd64.deb


#COPY docker-entrypoint.sh /usr/local/bin/docker-entrypoint.sh
#RUN ln -s /usr/local/bin/docker-entrypoint.sh /
#ENTRYPOINT ["docker-entrypoint.sh"]
COPY index.html /usr/local/apache2/htdocs/index.html
#CMD /etc/init.d/filebeat start && /etc/init.d/metricbeat start && httpd-foreground 

CMD /etc/init.d/filebeat start  && httpd-foreground 
