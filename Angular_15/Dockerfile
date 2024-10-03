FROM node:18.13.0

RUN apt-get update -qq && apt-get install -y vim
RUN npm update -g npm
RUN npm install -g @angular/cli@15.0.0

COPY ./sample-app /home/node/sample-app
WORKDIR /home/node/sample-app

EXPOSE 4200

CMD ["ng", "serve", "--host", "0.0.0.0"]