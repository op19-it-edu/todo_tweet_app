# FROM node:alpine AS builder

# WORKDIR /app

# RUN apk update && \
#     apk add git && \
#     git clone https://github.com/op19-it-edu/spa-server.git

# WORKDIR app/spa-server

# RUN npm install && \
#     npm run build

FROM nginx:alpine

# COPY --from=builder /app/dist /var/www/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]