# sqlite3 -> sqlite
# -db: create		// cree database for the current rails env
# -db: schema:load	// load le schema
# -db: seed

FROM ruby:latest

RUN apt-get update && apt-get install -y build-essential libpq-dev sqlite3 nodejs
RUN gem install rails 

ONBUILD COPY app/ /opt/app

ONBUILD RUN bundle install
ONBUILD RUN rails db:migrate
ONBUILD RUN rails db:setup
