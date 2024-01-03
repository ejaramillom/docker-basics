FROM postgres:14.5-alpine

RUN apk update && apk add --no-cache git build-base postgresql-client postgresql-dev

RUN git clone https://github.com/citusdata/pg_cron.git
RUN cd pg_cron && make && make install

RUN apk del git build-base postgresql-dev && \
    rm -rf /pg_cron

COPY init-db/ /docker-entrypoint-initdb.d

EXPOSE 5432

CMD ["postgres"]

# pg_cron.git

#!/usr/bin/env bash

set -e

# Variables
customconf="/var/lib/postgresql/data/custom-conf.conf"
conf="/var/lib/postgresql/data/postgresql.conf"

# Create custom config file
echo "shared_preload_libraries = 'pg_cron'" > "$customconf"
chown postgres "$customconf"
chgrp postgres "$customconf"

# Include custom config file in main config
if ! grep -qF "include = '$customconf'" "$conf"; then
  echo "include = '$customconf'" >> "$conf"
fi

# Restart PostgreSQL for the changes to take effect
service postgresql restart
