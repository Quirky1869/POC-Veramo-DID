# POC-Veramo-DID

## Contributeurs
|Contributeurs|
|:----------:|
|Mickael S.|
|Michael J.|

## Dockerfile
```Dockerfile
FROM node:lts
WORKDIR /app
RUN npm install -g tsx nodemon
COPY ./app/package.json /app/package.json
RUN npm install
CMD ["npm","run","prod"]
```

## docker-compose.yml
```yaml
services:
  app:
    build: .
    ports:
      - 7777:7777
    volumes:
      - ./app:/app
      - /app/node_modules
```