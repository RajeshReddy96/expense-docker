FROM node:20
EXPOSE 8080
ENV DB_HOST="mysql"
# we are creating use run  and opt means optional
RUN mkdir /opt/server
# use workdir to move directory
WORKDIR /opt/server
COPY package.json .
COPY *.js . 
RUN npm install
CMD ["node", "index.js"]