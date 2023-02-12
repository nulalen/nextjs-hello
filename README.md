# Next.jsお勉強
Next.jsお勉強用リポジトリ

このリポジトリをcloneしたら、```docker compose run --rm app yarn```を実行すれば、node_modulesのインストールができるはず。

## 初期構築
あらかじめsrcディレクトリを作成しておく
作成したら、生成コマンドを実行
```
docker compose run --rm app sh -c 'yarn create next-app . --typescript --network-timeout 600000'
```
yarnコマンドのESOCKETTIMEDOUTエラーによって失敗するため、タイムアウトまでの時間を延長する```--network-timeout```オプションを使用した

## Prettierのインストール
ESLintはNextjs v11.0.0以降create-next-appの際にインストールされるため、Prettierのみインストールする
```
docker compose run --rm app sh -c "yarn add -D prettier eslint-config-prettier --network-timeout 600000"
```

package.jsonの```script```に```format```を追加し、```yarn format```コマンドでPrettierを実行
できるように設定する
