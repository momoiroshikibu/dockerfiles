FROM ruby:2.4.0
RUN apt-get update -qq && apt-get install -y build-essential
WORKDIR /app
ADD Gemfile /app/Gemfile
RUN bundle install

