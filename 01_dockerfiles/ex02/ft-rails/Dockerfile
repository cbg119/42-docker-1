#docker build -t ft-rails:on-build .

FROM ruby

RUN apt-get update; apt-get -y upgrade; apt-get -y install sqlite3
RUN gem update; gem install rails

ONBUILD ARG DIR=./app/
ONBUILD WORKDIR /opt/app/
ONBUILD COPY $DIR .

ONBUILD RUN bundle install
ONBUILD RUN rake db:setup
ONBUILD RUN rake db:seed
