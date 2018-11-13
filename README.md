# 使い方
※ Do at your own risk.


.envを編集してください

```
SQUID_USERNAME=proxyuser
SQUID_PASSWORD=proxypassword
```


コンテナを起動

```
docker-compose up -d
```

秘密鍵を確認

```
docker-compose exec ssh cat id_rsa
```

表示された鍵を手元に保存してください(chmod 600を忘れずに)


コンテナを立てたホストあてに以下のsshコマンドで繋いでください

```
ssh root@192.168.2.8 -p 80 -i <さっき保存した秘密鍵ファイル> -L 9090:squid:3128
```

これでlocalhost:9090をブラウザでプロキシとして設定すればOK!!
proxyには.envで指定したユーザ/パスワードで接続できます。
