FROM ruby:3.0.5

# Node.jsをインストール
RUN curl -sL https://deb.nodesource.com/setup_20.x | bash - && apt-get install -y nodejs

# yarnパッケージ管理ツールをインストール
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
  && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list \
  && apt-get update -qq && apt-get install -y yarn

COPY ./src /app

ARG USERNAME=docker
ARG GROUPNAME=docker
ARG UID=1000
ARG GID=1000
RUN groupadd -g ${GID} ${GROUPNAME}
RUN useradd -u ${UID} -g ${GID} -s /bin/bash -m ${USERNAME}
RUN gpasswd -a ${USERNAME} sudo

USER ${USERNAME}

WORKDIR /home/${USERNAME}/app
COPY --chown=${USERNAME}:${GROUPNAME} ./src /home/${USERNAME}/app

RUN bundle config --local set path 'vendor/bundle' \
  && bundle install

RUN yarn add @babel/core@latest --dev \
  && yarn add @babel/plugin-transform-class-properties @babel/plugin-transform-object-rest-spread @babel/plugin-transform-private-methods @babel/plugin-transform-private-property-in-object --dev

EXPOSE 3000

CMD ["rails", "server", "-b", "0.0.0.0"]