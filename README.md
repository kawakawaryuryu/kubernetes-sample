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
