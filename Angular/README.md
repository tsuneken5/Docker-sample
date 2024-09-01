# ディレクトリ構成

```
$ tree -a -F --dirsfirst
.
├── sample-app/
├── .dockerignore
├── Dockerfile
├── README.md
└── docker-compose.yml
```


# 手順
## プロジェクトフォルダの作成
```
$ mkdir sample-app
```

## イメージのビルド
```
$ docker-compose build
```

## プロジェクトの作成
```
$ docker-compose run --rm angular ng new sample-app --directory .
```

## コンテナの起動
```
$ docker-compose up -d
```

# 確認
ブラウザから http://localhost:4200/ にアクセスして、Angularの画面が表示されれば成功。

# 解説（ブログ）
[Windows11 + WSL2 ＋ Docker で Anuglar開発環境を作成する](https://engineer.tsuneken5.com/2024/08/31/docker-angular/)