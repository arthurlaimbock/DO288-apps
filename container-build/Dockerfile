# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

EXPOSE 8080

LABEL io.openshift.expose-services="8080:http" \
      io.k8s.description="A Basic http server childer image, using ONBUILD" \
      io.k8s.display.name="Apache HTTP Server" \
      io.openshift.tags="apache, httpd"

RUN sed -ri -e '/^Listen 80/c\Listen 8080' /etc/httpd/conf/httpd.conf

RUN chgrp -R 0 /var/log/httpd /var/run/httpd && \
    chmod -R g=u /var/log/httpd /var/run/httpd

USER 1001
