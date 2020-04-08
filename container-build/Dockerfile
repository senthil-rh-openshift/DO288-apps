# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

EXPOSE 8090

LABEL io.openshift.expose-services="8090:http"

LABEL io.k8s.description="A complex Apache http parent image, uses Onbuild" \
      io.k8s.display-name="Apache http compounder" \
      io.openshift.expose-services="8090:http" \
      io.openshift.tags="apache, httpd"

RUN sed -i "s/Listen 80/listen 8090/g" /etc/httpd/conf/httpd.conf

RUN chgrp -R 0 /var/log/httpd /var/run/httpd &&
    chmod -R g=u /var/log/httpd /var/run/httpd

USER 501

