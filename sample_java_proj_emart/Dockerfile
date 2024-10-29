FROM node:14 AS ui-build
WORKDIR /usr/src/app
COPY ./client/ ./client/
RUN cd ./sample_java_proj_emart/client && npm install && npm run build

FROM node:14 AS server-build
WORKDIR /usr/src/app
COPY nodeapi/ ./nodeapi/
RUN cd ./sample_java_proj_emart/nodeapi && npm install

FROM node:14
WORKDIR /usr/src/app/
COPY --from=server-build /usr/src/app/nodeapi/ ./
COPY --from=ui-build /usr/src/app/client/dist ./client/dist
RUN ls
EXPOSE 4200
EXPOSE 5000
CMD ["/bin/sh", "-c", "cd /usr/src/app/ && npm start"]
