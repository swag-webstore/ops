各種手順
--
開発
-----
* 変更内容をイメージとして保存
```
docker commit <コンテナのhash値> swag/develop:<日付(yyyymm)>_<シーケンス番号>
※ シーケンス番号は日付毎に1に初期化し、commitの度にincrementしていく
```

* 保存したイメージをdocker hubに保存
```
docker push swag/develop:<日付(yyyymm)>_<シーケンス番号>
```

リリース
-----
* コンテナ用のイメージを取得
```
docker pull swag
```

* イメージからコンテナを作成
```
docker run -i -t -h swag_release -d -p 80:80 -p 2222:22 swag/develop:<日付(yyyymm)_<シーケンス番号>
```
