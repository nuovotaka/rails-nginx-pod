Podman compose で Rails 環境を構築する。
HOST：MacOS(intel)
Podman desktop を利用します。こちらに関してはそれぞれ公式よりインストールしてください。

こちらで使用する DB は`postgresql`です。
クローン後のコマンドは下記です。

```
podman compose build
```

```
podman compose up -d
```

コンテナ内に入るコマンドが下記です。

```
podman compose run web bash
```

コンテナ内で下記のコマンドを実行します。

```
bin/rails db:create
```

コンテナを抜ける

```
exit
```

podman desktop で web のゴミを削除する
`localhost:80`にアクセスすると初期画面が表示されると思います。

pgadmin4 でのアクセスは下記

```
メールアドレス：info@domain.com
パスワード：password
```

となっています。
