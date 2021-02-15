FROM swaggerapi/swagger-ui

RUN apk add \
        npm \
    && npm install -g @apidevtools/swagger-cli

COPY ./index.html /usr/share/nginx/html/index.html

# WORKDIR /usr/share/nginx/html
