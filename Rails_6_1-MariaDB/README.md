# 環境
 - Ruby: 3.0.5
 - Ruby on Rails: 6.1
 - MariaDB: 10.11

# ディレクトリ構成
```
$ tree --dirsfirst
.
├── src
│   ├── Gemfile
│   └── Gemfile.lock
├── Dockerfile
└── docker-compose.yml
```

# 手順

## イメージのビルド
```
$ docker-compose build
```

## プロジェクトの作成
```
$ docker-compose run --rm web rails new . --force --database=mysql
```

## イメージの再ビルド
```
$ docker-compose build
```

## データベースの設定・作成
config/database.ymlの password と host を編集
```
default: &default
  adapter: mysql2
  encoding: utf8mb4
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  username: root
  password: <%= ENV.fetch("DATABASE_PASSWORD") %>
  host: db
```

```
$ docker-compose run --rm web  rails db:create
```

## babel.config.jsの修正
@babel/plugin-proposal-* を @babel/plugin-transform-* に変更

## コンテナの起動
```
$ docker-compose up
```

ブラウザから http://localhost:3000/ にアクセス