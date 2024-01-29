FROM ruby:3.2.1

RUN apt-get update -qq && apt-get install -y postgresql-client
RUN mkdir /app
WORKDIR /app
ENV RAILS_LOG_TO_STDOUT='1' \
  RAILS_ENV='development'
COPY Gemfile /app/Gemfile
COPY Gemfile.lock /app/Gemfile.lock
RUN bundle install
COPY . /app

COPY docker/web/entrypoint.sh /usr/bin
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]

# EXPOSE 3000

# Start the main process.
CMD ["sh", "./docker/web/start-server.sh"]