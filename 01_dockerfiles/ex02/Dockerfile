FROM ruby:2.5.1

RUN apt-get update && \
    apt-get upgrade -y && \
    apt install nodejs postgresql-client -y
RUN mkdir /app
WORKDIR /app
# need to copy application app_git in ex02 directory
COPY app_git /app
RUN bundle install
ONBUILD WORKDIR /app
ONBUILD RUN bundler install
ONBUILD RUN rails db:migrate
ONBUILD RUN rails db:seed

# docker build -t ft-rails:on-build .
# docker build -t ex02 .
# docker run -it --rm -p 3000:3000 ex02