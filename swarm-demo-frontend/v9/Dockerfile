FROM ruby:2.4.3-alpine

RUN apk --no-cache add bash build-base postgresql-dev

WORKDIR /tmp
COPY Gemfile* ./
RUN bundle install

WORKDIR /app
COPY . .

EXPOSE 8080

ENTRYPOINT ["/app/docker-entrypoint.sh"]
CMD ["/usr/local/bin/bundle", "exec", "ruby", "app.rb"]

LABEL maintainer="julian@learndocker.online" website="https://LearnDocker.online"
