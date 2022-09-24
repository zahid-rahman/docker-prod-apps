FROM node:alpine as builder

WORKDIR '/app'

COPY /app/package.json . 

RUN yarn install

COPY /app .

RUN yarn run build

FROM nginx

COPY --from=builder /app/build /usr/share/nginx/html

