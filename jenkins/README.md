# Tips

## plugins.txtの作り方
Jenkinsにインストールするプラグインの一覧を`plugins.txt`で管理します。
プラグイン一覧は下記手順で作成します。
1. `http://localhost:20080/script` にアクセスし、下記コマンドを実行

```
Jenkins.instance.pluginManager.plugins.each{
  plugin ->
    println ("${plugin.getShortName()} ${plugin.getVersion()}")
}
```

2. 出力結果を`plugins.txt`にコピー
