FROM beevelop/ionic:v2021.06.1 AS ionic

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm ci

COPY . .
RUN ionic build --verbose

FROM nginx:alpine

COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html