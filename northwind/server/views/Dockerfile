FROM node:latest

ENV APP_DIR=/app APP_PORT=3000
ENV DB_USER=root DB_PASSWORD=changeit

WORKDIR ${APP_DIR}}

ADD main.js .
ADD package.json .
ADD package-lock.json .

ADD public public
ADD views views

#add healthcheck 
HEALTHCHECK --interval=30s --timeout=30s --start-period=15s --retries=3 \
    CMD curl -s -f http://localhost:${APP_PORT}}/health || exit 1

EXPOSE ${APP_PORT}

ENTRYPOINT [ "node" , "main.js"]

