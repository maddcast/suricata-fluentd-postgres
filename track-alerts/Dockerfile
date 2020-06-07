FROM fluent/fluentd:v1.11-1

# Use root account to use apk
USER root

# below RUN includes plugin as examples elasticsearch is not required
# you may customize including plugins as you wish
RUN apk add --no-cache --update --virtual .build-deps \
        build-base ruby-dev \
 && gem install fluent-plugin-sql \
 && apk add postgresql-client \
 && apk add postgresql-dev \
 && gem install pg \
 && gem install fluent-plugin-json-transform \
 && gem uninstall tzinfo -v 2.0.2 \
 && gem sources --clear-all \
 && apk del .build-deps \
 && rm -rf /tmp/* /var/tmp/* /usr/lib/ruby/gems/*/cache/*.gem

USER fluent
