FROM node:20 AS builder
WORKDIR /opt/server
COPY package.json .
COPY *.js . 
RUN npm install


FROM node:20.18.0-alpine3.20
EXPOSE 8080
ENV DB_HOST="mysql"
RUN addgroup -S expense && adduser -S expense -G expense && \
    mkdir /opt/server && \
    chown -R expense:expense /opt/server
WORKDIR /opt/server
COPY --from=builder /opt/server /opt/server
USER expense
CMD ["node", "index.js"]

# Before best practice implemented
# FROM node:20
# EXPOSE 8080
# ENV DB_HOST="mysql"
# # we are creating use run  and opt means optional
# RUN mkdir /opt/server
# # use workdir to move directory
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js . 
# RUN npm install
# CMD ["node", "index.js"]