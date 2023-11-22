FROM govpf/apache:2.4-alpine

USER root

ENV CONSUL_TEMPLATE_VERSION 0.35.0

RUN curl -L https://releases.hashicorp.com/consul-template/${CONSUL_TEMPLATE_VERSION}/consul-template_${CONSUL_TEMPLATE_VERSION}_linux_amd64.zip > /usr/local/bin/consul-template.zip \
      && unzip -d /usr/local/bin/ /usr/local/bin/consul-template.zip \
      && rm /usr/local/bin/consul-template.zip

ENTRYPOINT ["docker-entrypoint"]

WORKDIR /var/www/html
STOPSIGNAL SIGWINCH

USER apache
CMD ["apache2-foreground"]


