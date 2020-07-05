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
