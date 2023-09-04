version: '3.3'
networks:
  traefik:
    external: true
services:
  # non-sql database
  mongodb:
    container_name: backend
    image: mongo:latest
    restart: always
    volumes:
      - /data/mongo/docker:/data/db
    networks:
      - traefik
    ports:
      - 27017:27017
    environment:
      MONGO_INITDB_ROOT_USERNAME: ludus
      MONGO_INITDB_ROOT_PASSWORD: docker.2019.ludus
  # parse server
  parse:
    container_name: parse
    image: parse-server:latest
    restart: always
    networks:
      - traefik
    ports:
      - 1337:1337
    depends_on:
      - mongodb
    links:
      - mongodb
    environment:
      PARSE_SERVER_APPLICATION_ID: playludus_app_id
      PARSE_SERVER_MASTER_KEY: master_of_the_universe
      PARSE_SERVER_DATABASE_URI: mongodb://ludus:docker.2019.ludus@backend:27017/parse?authSource=admin
  # rest api
  api:
    container_name: rest
    build:
      context: ../
    restart: unless-stopped
    volumes:
      - /var/log/rest:/app/logs
    ports:
      - 6669:6669
    links:
      - mongodb
    depends_on:
      - mongodb
    networks:
      - traefik