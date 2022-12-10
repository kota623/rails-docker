FROM ruby:3.1.2
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs vim yarn
RUN mkdir /rails
WORKDIR /rails
ADD ./rails/Gemfile /rails/Gemfile
ADD ./rails/Gemfile.lock /rails/Gemfile.lock
ADD ./rails/.ruby-version /rails/.ruby-version

RUN bundle install
ADD ./rails /rails

EXPOSE 3000 12345 26162