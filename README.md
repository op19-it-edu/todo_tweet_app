### リポジトリの機能
`docker-compose` を使用し、以下のコンテナ群を同時に起動する

- api
- db（mysql）
- spa
  - Vue.jsで作成したSPAをnginxで配信する

### 起動手順
- リポジトリのルートに `config.json` と `.env` を配置する
  - [サンプル](https://github.com/op19-it-edu/todo_tweet_app/wiki)
- `docker-compose build --no-cache` で使用するイメージをビルドする
  - キャッシュが残っている場合、最新のイメージが利用されないことがあるため
- `docker-compose up -d` でコンテナ群を起動する
  - `api` が `db` を認識するのに1分程度かかるので少し待つ
- `http://localhost:80/signup` などでアクセスする
  - port番号は `.env` の `SPA_PORT` で指定した値
