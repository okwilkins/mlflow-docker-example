FROM postgres:16.0-bullseye

ARG POSTGRES_USER=postgres

COPY init_database.sh /docker-entrypoint-initdb.d/

USER ${POSTGRES_USER}
