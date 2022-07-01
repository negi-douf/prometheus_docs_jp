# Data Model

Prometheusの扱うデータは基本的に全て時系列のものである。Prometheusでは保存した時系列データを基に別の時系列データを生成することもできる。

## Metric names and labels

全ての時系列データは metric nameと labelとよばれるオプションの key-valueのペアで識別される。  

metric nameは計測される情報を示す。半角英数字と `:`、 `_` を含めることができる。ただし `:` は予約語？

同じ `GET /api/tracks` のようなメトリクスであっても、labelが異なれば別の時系列データとしてみなされる。クエリによる取得や生成なども別々に実行できる。
(ドキュメントでは dimension、次元が変わるといった書き方をしている)

labelの名称には半角英数字、 `_` を使用することができる。ただし、 `__` から始まるものは内部処理で予約されている。  
labelの値には unicodeの文字列を入れることができる。中身が空だった場合、そのラベルは存在しないものと扱われる。

## Notation

metric nameと labelは以下のように表記される。

```
<metric name>{<label name>=<label value>, ...}
```

たとえばこんな感じ。

```
api_http_requests_total{method="POST", handler="/messages"}
```

OIpenTSDBと同じらしい。
