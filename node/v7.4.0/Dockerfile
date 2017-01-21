# docker build -t node-v7.4.0 .
# docker run -it node-v7.4.0 node

FROM node:7.4.0

RUN apt-get update -y && apt-get upgrade -y

# yarn
RUN apt-get install apt-transport-https
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list

RUN apt-get update && apt-get install yarn
