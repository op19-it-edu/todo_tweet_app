### リポジトリの機能
`docker-compose`を使用し、以下のサーバ群を同時に起動する

- api-server
- db-server
- spa-server
- nginx

### 起動手順
- リポジトリのルートに`config.json`と`.env`を配置する
  - [サンプル](https://github.com/op19-it-edu/todo_tweet_app/wiki)
- `docker-compose build --no-cache`で使用するイメージをビルドする
  - キャッシュが残っている場合、最新のイメージが利用されないことがあるため
- `docker-compose up -d`でコンテナ群を起動する
