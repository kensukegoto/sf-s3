# slsでs3に静的サイトを上げる

- 静的サイトのみならば`sls create --template ...`で始まるテンプレ作成は不要
- 静的サイトを上げる用のプラグインをDL
  - `npm install --save serverless-finch`
- serverless.ymlを自作する
```yml
service: sf-s3（任意）

provider:
  name: aws
  region: ap-northeast-1

plugins:
  - serverless-finch（絶対必要）

custom:
  client:
    bucketName: sf-s3-20191104（任意）
````

- client/dist配下にhtmlファイルを置く
  - 静的サイトの置き場所であるclient/distを変更することも可能
- `serverless client deploy`でデプロイ＆変更
- `serverless client remove`で削除