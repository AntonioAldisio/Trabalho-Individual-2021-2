FROM ruby:3.0.0

RUN apt-get update && apt-get install -y build-essential libpq-dev nodejs
ARG SYSTEM=/home/aplicacao

WORKDIR ${SYSTEM}

COPY Gemfile ${SYSTEM}
COPY Gemfile.lock ${SYSTEM}

RUN gem install bundler && bundle install

COPY entrypoint.sh /usr/bin/
RUN chmod +x /usr/bin/entrypoint.sh
ENTRYPOINT ["entrypoint.sh"]

COPY . ${SYSTEM}
EXPOSE 3000