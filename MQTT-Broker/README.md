# フォルダ構成
```
 tree -a --dirsfirst
.
├── conf
│   └── mosquitto.conf
├── README.md
└── docker-compose.yml
```

# 前準備
TLS通信をしたい場合はsslディレクトリに証明書と秘密鍵を格納し、mosquitto.confのコメントアウトしている箇所を有効にしてください。

# コンテナの起動
```
$ docker-compose up -d
```

# 解説（ブログ）
[Windows11 + WSL2 ＋ Docker で MQTT Brokerを構築する](https://engineer.tsuneken5.com/2024/09/02/docker-mqtt-broker/)
