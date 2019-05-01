FROM node

RUN apt-get -y update && apt-get -y upgrade && apt-get -y instsall curl

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -

RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list

RUN apt-get update && apt-get install yarn

RUN yarn

EXPOSE 3000
