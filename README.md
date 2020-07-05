# nekochans-openapi
OpenAPIのスキーマを管理する

## APIスキーマの追加方法

`docs/` 以下に任意のディレクトリ名でディレクトリを作成し `openapi.yaml` を追加して下さい。

https://swagger.io/specification/ に以下の記述があるので `openapi.yaml` とするのが良さそうです。

>It is RECOMMENDED that the root OpenAPI document be named: openapi.json or openapi.yaml.

## OpenAPIの設計方針について

APIの設計方針に関しては以下のようなドキュメントを参考に設計します。

- [Web API 設計](https://docs.microsoft.com/ja-jp/azure/architecture/best-practices/api-design)
- [翻訳: WebAPI 設計のベストプラクティス](https://qiita.com/mserizawa/items/b833e407d89abd21ee72)

`openapi.yaml` には他にも色々と設定を行う必要がありますが、その点に関しては [スキーマファースト開発のためのOpenAPI（Swagger）設計規約](https://future-architect.github.io/articles/20200701/) を参考にしています。

## `openapi.yaml` から各言語のコードを生成する

- [openapi-generator](https://github.com/OpenAPITools/openapi-generator)
- [oapi-codegen](https://github.com/deepmap/oapi-codegen)

フロントエンドは `openapi-generator` がオススメです。

バックエンドは言語によりますがGoを使う場合 `oapi-codegen` をオススメします。

理由としてはOpenAPI3.0形式に対応しているからです。

Goだと [go-swagger](https://github.com/go-swagger/go-swagger) がもっとも有名ですがこのツールは残念ながらOpenAPI3.0形式に未対応です。

ただし `go-swagger` に関しては利用者が多い関係上、様々なノウハウが既に確立されているというメリットがあります。

[api-spec-converter](https://github.com/LucyBot-Inc/api-spec-converter) のようなツールを使って・・・

- `openapi.yaml` を3.0形式で書く
- `api-spec-converter` を利用して `openapi.yaml` を2.0形式に変換する

といった流れにする必要があります。

`go-swagger` を使う場合は [go-swaggerを用いたWebアプリケーション開発Tips19選](https://future-architect.github.io/articles/20200630/) という記事が参考になります。
