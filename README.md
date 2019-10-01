# kubernetes-sample
## 生成・更新
```
$ kubectl apply -f <manifest>
```

## 更新時に削除
`--prune`を付けてapplyするとマニフェストファイルの差分から消えたリソースを削除する  
`-l`でラベルを指定できる  
ラベルを指定しないとマニフェストファイルに書かれていないリソースは全て削除されるので注意
```
$ kubectl apply -f <manifest> --prune -l <label>
```

## 削除
マニフェストファイルで作成したリソースを削除するときに使用
```
$ kubectl delete -f <manifest>
```

## 自己署名証明書作成
IngressでHTTPSを利用する場合に証明書が必要のためSecretリソースとして作成
```
$ openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout tls.key -out tls.crt -subj "/CN=sample.example.com"
```

## Secret作成
```
$ kubectl create secret tls --save-config tls-sample --key tls.key --cert tls.crt
```
