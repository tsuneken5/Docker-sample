FROM node:18.17.0

RUN apt-get update -qq && apt-get install -y vim
RUN npm update -g npm
RUN npm install -g create-react-app

WORKDIR home/node/sample-app
USER node