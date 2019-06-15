# Visual Studio Code を ブラウザから使う

## 使い方
1. [docker, docker-compose をインストール](https://docs.docker.com/install/#supported-platforms)
1. 設定（任意）
    1. 設定ファイルを作成: [.env.example](./.env.example) を `.env` にコピー
        ```sh
        cp .env.example .env
        ```
    1. 設定ファイル `.env` を必要に応じて編集
        - ※ 同名の環境変数が定義されていると、 `.env` での定義より環境変数が優先される
        - ※ Docker Machine を使っている場合は、`code_server_bind_ip_port` には `127.0.0.0/8` のIPではなく、 `docker-machine ip` で得られるIPを設定する必要がある
            ```sh
            # code-server のbindをhost側につなげる際のhost側の待ち受けIP:PORT
            code_server_bind_ip_port=127.0.0.1:8443
            ```
            ```
            $ docker-machine ip
            192.168.99.100
            ```

1. サーバーを起動
    ```sh
    docker-compose up -d
    ```
1. ブラウザで `code_server_bind_ip_port` に指定したURLにアクセス
    - デフォルト: http://127.0.0.1:8443/

## Links
### 公式ページ
[Coder is an online IDE serving VSCode.](https://coder.com/)

### GitHub
[cdr/code-server: Run VS Code on a remote server.](https://github.com/cdr/code-server)

### Docker Hub
[codercom/code-server - Docker Hub](https://hub.docker.com/r/codercom/code-server)
