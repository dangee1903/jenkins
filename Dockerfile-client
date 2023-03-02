FROM node:16.14.0 as builder

ARG STAGE
ENV REACT_APP_STAGE $STAGE
ARG http_proxy
ENV http_proxy $http_proxy
ARG https_proxy
ENV https_proxy $https_proxy

RUN mkdir -p /usr/src/app/client
WORKDIR /usr/src/app/client

COPY ["./package.json", "./"]
RUN yarn install --pure-lockfile --network-timeout 1000000
COPY ["./", "./"]
RUN NODE_OPTIONS=--max_old_space_size=3072 yarn build
CMD ["yarn", "start"]


