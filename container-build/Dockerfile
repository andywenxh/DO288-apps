# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

# change the listen port from 80 to 8080
RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf


# change group and access mode for httpd
RUN chgrp -R 0 /var/log/httpd /var/run/httpd && \
chmod -R g=u /var/log/httpd /var/run/httpd

# use the user 1001 to launch app
USER 1001


# expose the new port 8080
EXPOSE 8080

LABEL io.k8s.description="A basic Apache HTTP Server child image, uses ONBUILD" \
io.k8s.display-name="Apache HTTP Server" \
io.openshift.expose-services="8080:http" \
io.openshift.tags="apache, httpd"



