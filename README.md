# POC-Veramo-DID

## Contributeur
|Contributeur|
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
      - 8080:8080
    volumes:
      - ./app:/app
```