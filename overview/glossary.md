# Glossary

### Alert

Prometheusのルールで評価され発出されるもの。Prometheusから Alertmanagerに送られる。

### Alertmanager

アラートを取り扱う。グループごとにまとめたり、重複を除いたり、上限に従ったりしつつ emailや Slackなどに送信する。

### Bridge

Prometheusからサードパーティのシステムに対しデータを公開する要素で、client libraryで実装される。Graphiteにメトリクスを出力できるものとして Python、Go、Javaなどにライブラリがあるもよう。

### Client library

メトリクスのプルをおこなうカスタムコレクタを実装する際や、メトリクスを Prometheusに出力する際などに、いくつかの言語を使うことができる (Go, Java, Python, Ruby, ...) 。client libraryはそれを簡単にするもの。

### Collector

exporterの一部で、メトリクスの 1セットを扱う。

### Direct instrumentation

client libraryを使ってコードの中に追加された計測処理？

### Endpoint

収集されるメトリクスのソースで、多くの場合はひとつのプロセスに相当する。

### Exporter

メトリクス収集元のアプリケーションと一緒に動いているバイナリ。Prometheusに対応した形式に変換したうえでデータを公開する。

### Instance

jobの中の対象を一意に識別するためのラベル。

### Job

同一の目的で 1つ以上のターゲットからデータを集めること。

### Notification

Alertmanagerによって発出される通知。

### Promdash

Prometheusのネイティブダッシュボードだが、今は非推奨。Grafanaが代替となっている。

### PromQL

Prometheus Query Language。柔軟な処理ができるもよう。

### Pushgateway

バッチジョブによって最新のメトリクスをプッシュするコンポーネント。ジョブが終わったら Prometheusがそれを収集できるようになる？

### Remote REead

Remetheusの機能のひとつで、クエリによって別のシステムから基本的な情報を取得するもの。

### remote Read Adapter

全てのシステムが remote readをサポートしているわけではない。この adapterが Prometheusと別のシステムを仲介し、データを変換してやりとりする。

### Remote Read Endpoint

remote readの対象となるシステム。

### Remote Write

Prometheusの機能のひとつで、収集したサンプルを他のシステムに送信できるようにするもの。

### Remote Write Adapter

全てのシステムが remote writeをサポートしているわけではない。この adapterが Prometheusと別のシステムを仲介し、データを変換してやりとりする。

### Remote Write Endpoint

remote writeの対象となるシステム。

### Sample

時系列のうち、特定の時点でのひとつの値。  
Prometheusでは、msecのタイムスタンプで float64のデータで構成される。

### Silence

alertmanagerの機能のひとつで、silenceラベルの付いたものを通知しない仕組み。

### Target

収集する情報を定義する情報。どんなラベルを適用するか、認証情報、どんなタイミングで収集するかなど...
