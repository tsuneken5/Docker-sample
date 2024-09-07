FROM mariadb:11.4.3

RUN groupmod -g 1000 mysql
RUN usermod -u 1000 mysql

# ユーザー切り替え
USER mysql