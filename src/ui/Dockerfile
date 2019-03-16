# FROM alpine:latest

# ADD gemrc /root/.gemrc

# ENV NOKOGIRI_USE_SYSTEM_LIBRARIES=1

# RUN apk update \
# && apk add ruby \
#            ruby-bigdecimal \
#            ruby-bundler \
#            ruby-io-console \
#            ruby-irb \
#            ca-certificates \
#            libressl \
#            less \
# && apk add --virtual build-dependencies \
#            build-base \
#            ruby-dev \
#            libressl-dev \
# \
# && bundle config build.nokogiri --use-system-libraries \
# && bundle config git.allow_insecure true \
# && gem install json --no-rdoc --no-ri \
# \
# && gem cleanup \
# && apk del build-dependencies \
# && rm -rf /usr/lib/ruby/gems/*/cache/* \
#           /var/cache/apk/* \
#           /tmp/* \
# /var/tmp/*
# ENV APP_HOME /app
# RUN mkdir $APP_HOME

# WORKDIR $APP_HOME
# ADD Gemfile* $APP_HOME/
# RUN bundle install
# ADD . $APP_HOME

# ENV POST_SERVICE_HOST post
# ENV POST_SERVICE_PORT 5000
# ENV COMMENT_SERVICE_HOST comment
# ENV COMMENT_SERVICE_PORT 9292

# CMD ["puma"]

FROM ubuntu:16.04
RUN apt-get update && apt-get install -y ruby-full ruby-dev build-essential && gem install bundler --no-ri --no-rdoc

ENV APP_HOME /app
RUN mkdir $APP_HOME

WORKDIR $APP_HOME
ADD Gemfile* $APP_HOME/
RUN bundle install
ADD . $APP_HOME

ENV POST_SERVICE_HOST post
ENV POST_SERVICE_PORT 5000
ENV COMMENT_SERVICE_HOST comment
ENV COMMENT_SERVICE_PORT 9292

CMD ["puma"]
