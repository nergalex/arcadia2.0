FROM mongo:latest

ENV MONGO_INITDB_DATABASE arcadia-db
ENV NAMESPACE default

COPY mongo-init.js /docker-entrypoint-initdb.d/