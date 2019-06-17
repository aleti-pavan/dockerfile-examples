FROM alpine:3.9

RUN apk --update --no-cache add \
    bash \
    python3 \
    terraform \
    ruby \
    ruby-bigdecimal \
    ruby-bundler \
    ruby-rdoc \
    ruby-webrick \
    && rm -rf /var/cache/apk/* /root/.cache/pip/*
RUN pip3 install --no-cache-dir --upgrade awscli pip
RUN mkdir -p /opt/al-techtest/
WORKDIR /opt/al-techtest/
RUN echo "source \"https://rubygems.org/\"" > Gemfile && \
    echo "gem 'rake'" >> Gemfile && \
    echo "gem 'awspec'" >> Gemfile && \
    bundle install
RUN awspec init
COPY ./ /opt/al-techtest/
